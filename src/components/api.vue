<!-- Este bloque define la estructura principal de la página utilizando Vue.js -->
<template>
    <div class="text-center bg-[#481800] p-8 rounded-md font-bold">
      <!-- Título y fecha -->
      <p class="text-blue-500  text-2xl italic font-bold ">
        
        Estado de la evaluación tutor del 2023b<br>
        al Martes 29 de Noviembre de 2023<br>
      </p>
      <br><br><br>
      <br>
      <!-- Contenedor flexible para organizar los bloques -->
      <div class="flex flex-col sm:flex-row justify-center items-center">
        <!-- Bloque 1 -->
        <div class="info-container info-container1 bg-blue-500 p-6 m-2 sm:w-1/2 rounded-md">
          <p>Periodo: {{ info.periodo }}</p>
        </div>
  
        <!-- Bloque 2 -->
        <div class="flex flex-col sm:w-1/2 m-2 items-center">
      <div class="info-container info-container2 bg-green-500 p-6 rounded-md">
        <p>Inicio: {{ formatDate(info.inicio) }}</p>
        <img src="../assets/inicio.png" alt=" " class="w-20 mx-auto mt-4">
      </div>
      <div class="info-container bg-yellow-500 p-6 mt-2 rounded-md">
        <p>Fin: {{ formatDate(info.fin) }}</p>
        <img src="../assets/fin.png" alt=" " class="w-20 mx-auto mt-4">
      </div>
    </div>
        
    <div class="flex flex-col sm:w-1/2 m-2 items-center">
      <div class="info-container bg-pink-300 p-6 rounded-md">
        <p>AlTotal: {{ info.alTotal }}</p>
        <img src="../assets/total.png" alt=" " class="w-20 mx-auto mt-4 rounded-md">
      </div>
      <div class="info-container bg-purple-500 p-6 mt-2 rounded-md">
        <p>AlEvaluados: {{ info.alEvaluados }}</p>
        <img src="../assets/evaluados.png" alt=" " class="w-20 mx-auto mt-4">
      </div>
    </div>
        
        
      </div>
    </div>
   
  
  
  
  </template>
  
  <!-- Este bloque utiliza el sistema de scripts de Vue 3 para manejar la lógica y el ciclo de vida del componente -->
  <script setup>
  import { onMounted, ref } from 'vue';
  
  // Variables reactivas
  const info = ref('');
  const isLoading = ref('');
  
  // Función para obtener datos de la API
  async function fetchData() {
    try {
      const response = await fetch('https:/sitmotul.com.mx/api/statusEval');
      const data = await response.json();
      info.value = data;
      isLoading.value = false;
      console.log(data);
    } catch (error) {
      console.error('Error al obtener datos:', error);
    }
  }
  
  //  que se ejecuta después de que el componente se monta
  onMounted(() => {
    fetchData();
  });
  
  // Función para formatear la fecha
  function formatDate(fecha) {
    const meses = ["Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre"];
  
    const fechaActual = new Date(fecha);
    const dia = fechaActual.getDate();
    const mes = meses[fechaActual.getMonth()];
    const año = fechaActual.getFullYear();
  
    return `${dia} de ${mes} de ${año}`;
  }
  </script>
  