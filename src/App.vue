<template>
  <div id="app">
    <navbar/>
    <div>
      <router-view/>
    </div>
  </div>
</template>

<style>
  * {
    box-sizing: border-box !important;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }

  body {
    margin: 0;

  }
</style>
<script>
  import Navbar from "./components/navbar";
  export default {
    components: {Navbar}
  }
</script>