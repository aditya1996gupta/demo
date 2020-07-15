<template>
<div class='app'>
<div id='a'>
<router-link to="/">Home </router-link> ||
<router-link to="about">demo</router-link>
</div>
<router-view />
</div>
</template>

<script>
export default {
  name: 'app',
  components: {
  }
}
</script>

<style>
.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   color: #2c3e50;
   margin-top: 20px;
}
#a{
display: flex;
justify-content: center;
 left: 0;
 top: 0;
 width: 100vw;
}
</style>
