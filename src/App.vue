<template>
  <div id="app" class="container-fluid mt-3">
    <div class="jumbotron">
      <Codificacion />
    </div>
    
  </div>
</template>

<script>
import Codificacion from './components/Codificacion.vue'


export default {
  name: 'App',
  components: {   
    Codificacion
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.jumbotron {
  padding: 32px !important;
}
</style>
