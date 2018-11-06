<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <nav>
      <router-link to="/">Home</router-link><br>
      <router-link to="/login">Login</router-link><br>
      <router-link to="/register">Register</router-link>
    </nav>
    <br>
    <router-view/>
  </div>
</template>

<script>
//import Login from './components/Login.vue'

export default {
  name: 'app',
  components: {
    //Login
  }
}
</script>

<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body { 
  background: #2a4072 !important; 
  overflow-x: hidden;
} 
</style>
