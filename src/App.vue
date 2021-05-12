<template>
  <h1>This is my first vue app.</h1>
  <p>Created By:- {{name}}</p>
  <h2>{{greet}} {{name}}</h2>
  <strong v-text="channel"></strong>
  <p v-html="bindhtml"></p>
  <div v-html="voucher"></div>
  <br>
  <p v-bind:id="headingId">Heading</p>
  <button v-bind:disabled="isdisabled">Click Me</button>
  <p class="underline">This text has underline class</p>
  <p v-bind:class="ispromoted && 'promoted'">Promoted Product</p>
  <p>If soldout movie color red else green.</p>
  <h3 v-bind:class="isSoldOut?'sold-out':['new', 'promoted']">InterStellar</h3>
  <h3 v-bind:class="[isSoldOut?'sold-out':'new', ispromoted && 'promoted' ]">Array Conditional Movie</h3>
  <h3 v-bind:class="{
    promoted: ispromoted,
    new: !isSoldOut,
    'sold-out': isSoldOut,
  }">
    Object Conditional Movie
  </h3>
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
      voucher:`<a href="#" onclick="alert('You got it!')">Grab your voucher</a>`,
      headingId: 'heading',
      isdisabled: false,
      ispromoted: true,
      isSoldOut: true,
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

.underline{
  text-decoration: underline;
}
.promoted{
  font-style: italic;
}
.new{
  color: green;
}
.sold-out{
  color: red;
}
</style>
