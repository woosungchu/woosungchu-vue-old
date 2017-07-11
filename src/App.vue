<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
* {
 margin: 0;
 padding: 0;
}

html,body {
  height:100%;
  width:100%;
}

#app {
  font-family: 'Graphik','Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  min-height: 700px;
}
</style>
