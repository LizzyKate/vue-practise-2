<template>
<div>
  <nav class="navbar navbar-expand-lg navbar-light bg-light"  >
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav"  >
    <ul class="navbar-nav"  >
      <li class="nav-item" v-for="(link, i) in item" :key="i" v-on:click="makeActive(link.code)" >
        <a class="nav-link " href="#" :class="{'create': link.code === service}">{{link.list}}</a>
      </li>
    </ul>
  </div>
</nav>
<p>You Chose {{service}}</p>
<div class="text-center mt-5" >
  <div  v-if="showToolTip">
  <input type="text" v-model="textContent" class="bg-primary mb-5 w-50" >
  </div>
<p v-on:click="toggleToolTip()">{{textContent}}</p>
</div>
</div>
</template>

<script>
export default {
  data(){
    return{
      service:'home',
      item:[
        {code:"home", list:"Home"},
        {code:"project", list:"Features"},
        {code:"services", list:"Pricing"},
        {code:"contact", list:"Contact"}
      ],
      textContent:'Edit Me',
      showToolTip:false
    }
  },
  methods:{
    makeActive: function(word){
      this.service = word;
    },
    toggleToolTip: function(){
      this.showToolTip = !this.showToolTip
    }
  }
}
</script>

<style scoped>
.create{
    background-color:#e35885;
}

</style>
