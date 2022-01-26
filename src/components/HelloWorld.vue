<template>
  <div class="hello">
    <input type="number" v-model.number="inOne" placeholder="Podaj liczbę">
    <input type="number" v-model.number="inTwo" placeholder="Podaj liczbę">
    <button @click='add(inOne, inTwo)'>dodaj</button>
    <div class='boxrad'>
      <p class='ppp'>Wynik w dziecku : {{newVal}}</p>
      <p class='ppp'>Wiadomość od Rdzoca : " {{msgd}} " </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msgd: String
  },
    data() {
    return {
      newVal: 'Hello Mars',
    }
  },
  methods:{
    add(e, b){
      if(typeof(e)!='number' || typeof(b)!='number'){
        this.newVal="Nie podałeś liczb"
      }else{
      this.newVal = e + b
      this.$emit('childMsg', e + b)
      }d
    }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
 border-radius: 5px;
 background-color: white;
 width: 500px;
 margin-top: 100px;
 padding-top:10px ;
 margin-bottom: 50px;
}
input{
  border: none;
  border-radius: 5px;
  background-color: rgb(224, 224, 224);
  margin: 10px;
  padding: 10px;
  outline-color: rgb(218, 218, 218);
}
button{
  color: white;
  border: none;
  border-radius: 5px;
  background-color: rgb(97, 153, 255);
  margin: 10px;
  padding: 10px;
  box-shadow: 2px 1px 4px  rgb(139, 141, 163);
  
}
button:hover{
  box-shadow: none;
}
button:active{
  background-color: rgb(59, 128, 255);
}
.boxrad{
  width:100%;
  background-color: rgb(97, 153, 255);
  padding: 10px 0px;
  margin-top:30px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
}
</style>
