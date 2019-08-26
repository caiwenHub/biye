<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html{
  font-size: 50px;
}
body{
  font-size: 14px;
  background: #f7f7f7;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
li{
  list-style: none;
}
</style>
