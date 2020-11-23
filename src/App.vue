<template>
  <div id="app">
    <Nav/>
    <mainImage/>
    <UserList/>  
  </div>
</template>
<script>
  import UserList from './components/UserList.vue';
  import Nav from './components/Nav.vue';
  import mainImage from './components/mainImage.vue'
  export default {
    name: 'App',
    components: {
      UserList,
      Nav,
      mainImage
    }
  }
</script>
<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>
