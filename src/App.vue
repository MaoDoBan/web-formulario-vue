<template>
  <Formulario />
</template>

<script>
import Formulario from "./components/Formulario.vue"

export default {
  name: 'App',
  components: { Formulario }
}
</script>

<style>
#app{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  margin: 0;
  background: #aaa;/*rgb(55, 57, 62);*/
}
</style>
