<template>
  <div class="app-background">
    <div class="container">
      <h1 class="title">Buscar Vehículo</h1>
      <input v-model="query" placeholder="Ingrese la placa patente o VIN" class="input-field" />
      <button @click="searchVehicle" class="btn btn-primary search-button">Buscar</button>
      <div v-if="errorMessage" class="error-message">{{ errorMessage }}</div>
      <div v-if="vehicle" class="vehicle-info">
        <p><strong>Marca:</strong> {{ vehicle.brand }}</p>
        <p><strong>Modelo:</strong> {{ vehicle.model }}</p>
        <p><strong>Año:</strong> {{ vehicle.year }}</p>
        <p><strong>Cilindrada:</strong> {{ vehicle.displacement }}</p>
        <p><strong>VIN:</strong> {{ vehicle.vin }}</p>
        <p><strong>Número de Motor:</strong> {{ vehicle.engine_number }}</p>
        <p><strong>Versión:</strong> {{ vehicle.version }}</p>
        <p><strong>Placas:</strong> {{ vehicle.plates.join(', ') }}</p>
        <p><strong>Propietario Actual:</strong> {{ vehicle.current_owner }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      query: '',
      vehicle: null,
      errorMessage: ''
    };
  },
  methods: {
    async searchVehicle() {
      try {
        const response = await axios.get(`http://localhost:8000/api/vehicle/search`, {
          params: { query: this.query }
        });
        this.vehicle = response.data;
        this.errorMessage = '';
      } catch (error) {
        console.log('Error:', error); // Para depuración
        if (error.response) {
          this.errorMessage = error.response.data.message || 'Error desconocido';
        } else {
          this.errorMessage = 'Error en la conexión';
        }
        this.vehicle = null; // Limpiar datos del vehículo en caso de error
      }
    }
  }
};
</script>

<style scoped>
body, html {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

.app-background {
  background: url('@/assets/images/fondo.jpg') no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  max-width: 700px;
  padding: 20px;
  background-color: rgba(0, 0, 0, 0.6); /* Fondo negro semi-transparente */
  border-radius: 8px;
  box-shadow: 0 0 12px rgba(0, 0, 0, 0.3);
  color: #fff; /* Texto en blanco */
}

.title {
  text-align: center;
  color: #fff;
  font-size: 24px;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px #000; /* Sombra al texto */
}

.input-field {
  width: calc(100% - 22px);
  padding: 12px;
  margin: 10px 0;
  border: 2px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
}

.search-button {
  width: 100%;
  padding: 12px;
  border-radius: 4px;
  font-size: 16px;
  margin-top: 10px;
}

.error-message {
  color: #d9534f;
  font-weight: bold;
  text-align: center;
  margin-top: 10px;
}

.vehicle-info {
  background-color: rgba(255, 255, 255, 0.1); /* Fondo semi-transparente */
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  margin-top: 20px;
  color: #fff; /* Texto en blanco */
  font-size: 18px;
  text-shadow: 1px 1px 2px #000; /* Sombra al texto */
}

.vehicle-info p {
  margin: 10px 0;
}

.vehicle-info strong {
  color: #ffd700; /* Color para destacar los títulos en amarillo */
}
</style>


