<template>
  <div id="app">
    <GestionDeNotas/>
  </div>
</template>

<script>
import GestionDeNotas from "@/components/GestionDeNotas";

export default {
  name: 'App',
  components: {
    GestionDeNotas
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
  margin: 20px;
}
</style>
