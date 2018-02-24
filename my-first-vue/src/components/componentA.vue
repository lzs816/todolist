<template>
  <div class="hello">
      <h1>{{msg}}</h1>
      <h1>{{msgfrom}}</h1>
      <button @click="onClickMe">click!</button>
  </div>
</template>

<script>
export default {
  data: function(){
      return {
          msg: 'hello from componentA'
      }
  },
  props: ['msgfrom'],
  methods:{
      onClickMe: function(){
          console.log(this.msgfrom)
      }
  }
}
</script>

<style>
    h1{
        color:red;
    }
</style>


