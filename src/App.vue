<template>
  <router-view/>
</template>

<script>


export default {
  name: 'App',

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
  */
}

body {
  margin: 50px;
  background: #FAFAFA;
}
@media(max-width:500px) {
  body{
    margin: 30px;
  }
}
</style>
