<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <GreetMessage />
    <h1>Hello, {{ hello }}</h1>
    <h1 v-html="channel"></h1>
    <h1 v-text="channel"></h1>
    <div v-html="hack"></div>
    <button v-bind:disabled="disable" onclick="alert('may name is lakhan')">Bine me</button>
    <h3 v-bind:class="status" class="underline">text underline</h3>
    <h2 v-bind:class="isstatus ? 'new': 'old'">Movie? old</h2>
    <div v-bind:style="{background:color,'font-size':num+'px'}"> yeh duniya yeh mehfil</div>
     <!-- list rendering -->
    <li v-bind:style="{textDecoration:none,
    listStyle:none}" v-for="name in names" :key="name">{{ name }}</li>
    <!-- event handeling -->
    <h2 >{{ name }}</h2>
    <button v-on:click="name='batman'">click me!</button>

    

  </div>
</template>

<script>
import GreetMessage from './components/Greet.vue'
export default {
  name: 'App',
  data() {
    return {
      hello: 'namaste', // Removed the semicolon here
      channel: `<b>salam namaste!!</b>'`,
      hack:`<a href="#" onclick="alert('you have clicked me')">Click me!!</a>`,
      //binding to attributes
      disable:false,
      status:'danger',
      isstatus:false,
      color:'red',
      num:50,
      names:["bruce","bayene","batman"],
      name:'pritam'
    }
  },
  components:{
    GreetMessage,
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
.underline
{
  text-decoration:underline ;
}
.new
{
  color:red;
}

.old
{
  color:green;
}
</style>
