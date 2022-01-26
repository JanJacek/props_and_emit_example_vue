<template>
<div id='app'>
<hello-world @childMsg="promptThis" :msgd="msg"/>
<p> Wynik w rodzicu {{odp}}</p>
</div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return{
      odp:'Hello World',
      msg:'Pawiany wchodzą na sciany',
      elo:'/img/explo.94ca6203.gif'
    }
  },
  methods:{
    promptThis(e){
      console.log(e);
      this.odp = e
    }
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color:rgb(224, 224, 224) ;
  height: 100%;
  display:flex;
  justify-content:center;
}
p{
  color:rgb(133, 133, 133);
  margin-left:10px;
  font-weight: bold;
}
p.ppp{
  color:white;
}
</style>
