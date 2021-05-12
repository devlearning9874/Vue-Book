<template>
  <h1>This is my first vue app.</h1>
  <p>Created By:- {{name}}</p>
  <h2>{{greet}} {{name}}</h2>
  <strong v-text="channel"></strong>
  <p v-html="bindhtml"></p>
  <div v-html="voucher"></div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      greet:'Hello',
      name:"Abhishek",
      channel:'Myblogeater',
      bindhtml:'<i>Binding Html</i>',
      voucher:'<a href="#" onclick="alert(You got it!)">Grab your voucher</a>',
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
