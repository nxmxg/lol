<template>
  <div id="app">
    <img src="./assets/logo.png">
    <MyComponent @msgEvent="getMsg" title="儿子，干啥额" :age='age' :names="names"/>
    {{ msg }}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Learn from "./components/learn"
import InputComponent from "./components/InputComponent"
import MyComponent from './components/MyComponent'

export default {
  name: 'App',
  data(){
    return{
      age:20,
      names:["iwen","ime","ice"],
      msg:""
    }
  },
  components: {
    HelloWorld,
    Learn,
    InputComponent,
    MyComponent // 注入
  },
  methods:{
    getMsg(value){
      this.msg = value;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
