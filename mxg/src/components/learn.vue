<template lang="html">
  <div class="learn">
    <ul>
      <li v-for="(item,index) in names" :key="index">{{ item }}</li>
    </ul>
    <button @click="pushClickHandler" type="button" name="button">add</button>
    <p>{{ getHello }}</p>
    <p>{{ setAuthor }}</p>
    <p>{{ msetAuthor() }}</p>
    <input v-model="msg" type="text" name="" value="">
    <div :class="obj">
      是否看得见
    </div>
    <div :class="[hello+'1',world]">hello,world!</div>
    <div :class="[flag ? 'flag':'']">文本</div>
    <div :class="[hello,{'active':isActive,'error':isError},flag ? 'flag':'']">嵌套效果</div>
    <div :style="{fontSize:currentSize+'px',color:'red'}">动态内联样式</div>
    <div :style="[baseStyles]">
      数组内联
    </div>
  </div>
</template>

<script>
export default {
  name:"Learn",
  data(){
    return{
      names:["iwen","ime","frank"],
      hello:"hello",
      world:'world',
      jinyong:"鹿鼎记",
      gulong:'六指琴魔',
      msg:"", // 初始化
      isActive:true,
      isError:true,
      obj:{
        active:true,
        error:false
      },
      flag:true,
      currentSize:30,
      baseStyles:{
        fontSize:"40px",
        color:"green",
        border:"1px solid green",
        borderRadius:"10px"
      }
    }
  },
  methods:{
    pushClickHandler(event){
      // this.names.push("sukura");
      var newNames = this.names.concat(["sukura","ice"])
      this.names = newNames;
    },
    msetAuthor(){
      return this.gulong + "---古龙"
    }
  },
  computed:{
    getHello(){
      return this.hello.split('').reverse().join('')
    },
    setAuthor(){
      return this.jinyong + "---金庸"
    }
  },
  watch:{
    msg(value){
      if(value === "1000"){
        console.log("证书");
      }
      console.log(value);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
