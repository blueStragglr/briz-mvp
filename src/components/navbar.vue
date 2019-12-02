<template>
  <div id="nav">
    <div class="nav-logo">
      <img class="logo" src="../../src/assets/2x/logo_briz.png" @click="moveTo('/')">
    </div>
    <div class="nav-buttons">
      <router-link to="/">Main</router-link>&nbsp; | &nbsp;
      <router-link to="/" @click="alert('non implemented')">Log in</router-link>
    </div>
  </div>
</template>

<script>
  export default {
    name: "navbar",
    methods: {

      moveTo(path){
        this.$router.push(path)
      }

    }

  }
</script>

<style scoped>



#nav {
  padding: 10px;
  height: 64px;
  display: flex;
  align-items: center;
  align-content: center;
  text-align: center;
  /*box-shadow: 0 0 2px 4px rgba(0, 0, 0, 0.05);*/
}

.logo{
  flex: 0;
  height: 24px;
  margin: 14px;
  cursor: pointer;
}

.nav-buttons a{
  color: #393638 !important;
  font-weight: 500 !important;
  text-decoration: none;
}
.nav-buttons{
  flex: 1;
  text-align: right;

}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>