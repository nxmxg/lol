<template lang="html">
  <div class="mycomponent">
    Hello:{{ title }}-{{ age }}
    <ul>
      <li v-for="(item,index) in names" :key="index">{{ item }}</li>
    </ul>
    <button @click="sendMsg" type="button" name="button">send</button>
  </div>
</template>

<script>
export default {
  name:"MyComponent",
  data(){ // state 或者是小程序中的data
    return {
      msg:"我是儿子的数据"
    }
  },
  props:{
    title:{
      type:String,
      required:true
    },
    age:{
      type:[Number,String],
      default:100 // 必须是基本类型，如果是数组或者是对象必须返回一个function
    },
    names:{
      type:Array,
      default:function(){
        return [10,20,30]
      }
    }
  },
  methods:{
    sendMsg(event){
      // 参数1：自定义事件名称   参数2：传递的数据
      this.$emit("msgEvent",this.msg)
    }
  }
}
</script>

<style lang="css" scoped>

</style>
