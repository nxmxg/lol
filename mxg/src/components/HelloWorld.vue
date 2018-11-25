<template>
  <div class="hello">
    {{ msg }}
    {{ 1+1 }}
    {{ '1+1' }}
    {{ arr[1] }}
    {{ 10>9 ? '对的' : '出错' }}
    <div v-html="myh1"></div>
    <div v-bind:class="myclass">哈哈哈</div>
    <template v-if="flag">
      <p>孙悟空</p>
      <p>齐天大圣美猴王</p>
    </template>
    <template v-else>
      <p>六耳猕猴</p>
      <p>通臂猿猴</p>
    </template>
    <p v-show="flag">p1</p>
    <p>p2</p>
    <ul>
      <li v-for="(item,index) in names" v-bind:key="index">{{ item }}-{{ index }}</li>
    </ul>
    <p v-for="(value,key,index) in obj" v-bind:key="index">{{value}}-{{key}}-{{index}}</p>
    <button v-on:click="counter += 1" type="button" name="button">add</button>
    <p>{{ counter }}</p>
    <button @click="getMessage('hello',$event)" type="button" name="button">按钮</button>
    <p v-once>{{ message }}</p>
    <a href="#" v-on:click.prevent="goPage">去某个页面</a>
    <div :class="hello">hh1</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      message:0,
      counter:0,
      msg: '欢迎来到vue的世界',
      arr:[10,20,30],
      myh1:"<h1>hello</h1>",
      myclass:'hello1',
      flag:false,
      names:["iwen","ime","frank"],
      obj:{
        name:"iwen",
        age:"29"
      },
      hello:"hh1"
    }
  },
  methods:{
    getMessage:function(value,event){
      // message每次加10
      this.message += 10;
      console.log(this.message);
      console.log(value);
      console.log(event); // 原声event对象
    },
    goPage(event){
      // event.preventDefault()
      console.log("去吧");
    }
  }
}
</script>

<style scoped>

</style>
