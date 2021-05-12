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
  <p v-bind:style="{
    color:textColor,
    fontSize:fSize + 'px',
    padding:'25px' 
  }">Styling Text</p>
  <p v-bind:style="headerStyleObject">Style Object</p>
  <p v-bind:style="[baseStyleObject, successStyleObject]">Success Style</p>
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
      textColor: "orange",
      fSize : 50,
      headerStyleObject:{
        color: 'green',
        fontSize: '50px',
        padding:'15px',
      },
      baseStyleObject:{
        color: 'red',
        fontSize: '50px',
        padding:'15px',
      },
      successStyleObject:{
        color: 'blue',
        backgroundColor:'lightgreen',
        border: '1px solid green',
        padding: '20px',
      }
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
