<template>
    <h1 @click="gogogo">about</h1>
</template>

<script>
export default {
  components: {},
  methods:{
      gogogo(){
          window.location.href='./impress/me.html';
      }
  }
};
</script>

<style lang="less" scoped>
h1{
    cursor: pointer;
}
</style>