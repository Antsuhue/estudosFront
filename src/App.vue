<template>
  <div id="app">
    <img src="./assets/logo.jpg" alt="Logo Bank">
    <NavBar />
    <Body />
  </div>
</template>

<script>
import NavBar from './components/Navbar.vue'
import Body from './components/Cadastro.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Body
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
  margin-top: 10px;
  margin-left: 10%;
  margin-right: 10%;
}
img{
  margin-bottom: 1%;
}
</style>
