<template lang="html">
  <div class="input">
    <input type="text" v-model.trim="msg" name="" value="">
    <p>{{ msg }}</p>
  </div>
</template>

<script>
export default {
  name:'InputDemo',
  data(){
    return{
      msg:""
    }
  }
}
</script>

<style lang="css" scoped>
</style>
