<template>
  <div id="app">
    <div id="nav">
      <div class="nav-logo">

      </div>
      <div class="nav-buttons">
        *디버그용 임시 버튼
        <router-link to="/">Home</router-link>
        |
        <router-link to="/detailPage">Item detail</router-link>
      </div>
    </div>
    <router-view/>
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
    text-align: center;
    color: #2c3e50;
  }

  #nav {
    padding: 10px;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: center;
    text-align: center;
    box-shadow: 0 0 2px 4px rgba(0, 0, 0, 0.05);
  }

  #nav a {
    font-weight: bold;
    color: #2c3e50;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }

  body {
    margin: 0;

  }
</style>
