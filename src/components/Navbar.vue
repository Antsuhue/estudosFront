<template>
  <div>
    <b-nav pills align="center">
      <b-nav-item active >Início</b-nav-item>
      <b-nav-item>Transferência</b-nav-item>
      <b-nav-item>Depósito</b-nav-item>
      <b-nav-item>Login</b-nav-item>
    </b-nav>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.nav-pills .nav-link.active, .nav-pills .show > .nav-link{
  background-color: black;
}

.nav-link{
  color: black;
}


h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
