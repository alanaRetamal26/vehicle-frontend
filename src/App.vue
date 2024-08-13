<template>
  <div id="app">
    <h1>Informacion del vehiculo en el sistema</h1>
    <search-vehicle></search-vehicle> <!-- Componente de búsqueda -->
  </div>
</template>

<script>
import SearchVehicle from './components/SearchVehicle.vue';

export default {
  name: 'App',
  components: {
    SearchVehicle
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
