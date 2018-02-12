<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'Calculator'
  }
</script>

<style>
@import url(https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css);
 body{
    margin: 0 0 0 0;
    font-family: 'NanumSquare';
  }
  #app{
    width: 100%;
    height: 100%;
  }
</style>
