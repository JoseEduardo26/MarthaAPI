
<template>
    <div class="text-center  bg-[#481800] p-8 rounded-md  font-bold">
      <p class="text-blue-500 text-2xl italic font-bold ">
        Carreras <br>
        Periodo 2023B<br>
        Estado de la evaluación por ingeniería 
      </p>
      <br>
      <div class="flex flex-wrap justify-center">
        <div class="info-container info-container1 bg-purple-500 rounded-md">
          <p class="px-2 text-center"  v-if="info.ISC">ISC: Listas {{ info.ISC.listas }}, Faltantes {{ info.ISC.faltantes }}</p>
          <img src="../assets/ISC.png"  class="w-50 mx-auto mt-4 md:w-3/4">
  
          <label class="px-2 text-center"  v-if="info.ISC">Porcentaje completado: {{ Math.round(((info.ISC.listas - info.ISC.faltantes) / info.ISC.listas) * 100) }}%</label>
     <br>
     <div class="md:flex flex-row mb-5 mt-5">
          <label class="md:px-2">0%</label>
          <div class="bg-gray-300 w-full rounded-lg mt-1 ">
            <div v-if="info.ISC" class="h-full bg-[#ff4444] rounded-lg" :style="{ width: `${Math.round(((info.ISC.listas - info.ISC.faltantes) / info.ISC.listas) * 100)}%` }"></div>
         </div>
          <label class="md:px-2">100%</label>
        </div>
      <p class="px-2 text-center" v-if="info.ISC" :style="{ color: (info.ISC.faltantes === 0) ? 'green' : 'darkred' }"> Porcentaje Faltante: {{ Math.round((info.ISC.faltantes / info.ISC.listas) * 100) }}%</p>
  
        </div>
  
        <div class="info-container info-container2  bg-pink-300 sm:w-1/2 rounded-md">
          <p class="px-2 text-center" v-if="info.IEM">IME: Listas{{ info.IEM.listas }}, faltantes {{ info.IEM.faltantes }}</p>
          <img src="../assets/IEM.png" alt=" " class="w-1/2 h-10 mx-auto  md:w-1/2 md:h-auto">
  
  
          <label class="px-2 text-center" v-if="info.IEM">Porcentaje completado: {{ Math.round(((info.IEM.listas - info.IEM.faltantes) / info.IEM.listas) * 100) }}%</label>
     <br>
     <div class="md:flex flex-row mb-5 mt-5">
          <label class="md:px-2">0%</label>
          <div class="bg-gray-300 w-full rounded-lg mt-1 ">
            <div v-if="info.IEM" class="h-full bg-[#ff4444] rounded-lg" :style="{ width: `${Math.round(((info.IEM.listas - info.IEM.faltantes) / info.IEM.listas) * 100)}%` }"></div>
         </div>
          <label class="md:px-2">100%</label>
        </div>
      <p class="px-2 text-center" v-if="info.IEM" :style="{ color: (info.IEM.faltantes === 0) ? 'green' : 'darkred' }"> Porcentaje Faltante: {{ Math.round((info.IEM.faltantes / info.IEM.listas) * 100) }}%</p>
  
        
  
        </div>
        <label v-if="info.IME">Porcentaje completado: {{ Math.round(((info.IEM.listas - info.IEM.faltantes) / info.IEM.listas) * 100) }}%</label>
     <br>
        <div class="info-container info-container3 bg-yellow-500 sm:w-1/2 rounded-md">
          <p class="px-2 text-center" v-if="info.IER">IER: Listas{{ info.IER.listas }}, faltantes {{ info.IER.faltantes }}</p>
          <img src="../assets/IER.png" alt=" " class="w-3/4 h-10 mx-auto  md:w-3/4 md:h-auto mt-4 mb-4">
  
  
          <label  v-if="info.IER">Porcentaje completado: {{ Math.round(((info.IER.listas - info.IER.faltantes) / info.IER.listas) * 100) }}%</label>
     <br>
     <div class="md:flex flex-row mb-5 mt-5">
          <label class="md:px-2">0%</label>
          <div class="bg-gray-300 w-full rounded-lg mt-1 ">
            <div v-if="info.IER" class="h-full bg-[#ff4444] rounded-lg" :style="{ width: `${Math.round(((info.IER.listas - info.IER.faltantes) / info.IER.listas) * 100)}%` }"></div>
         </div>
          <label class="md:px-2">100%</label>
        </div>
      <p v-if="info.IER" :style="{ color: (info.IER.faltantes === 0) ? 'green' : 'darkred' }"> Porcentaje Faltante: {{ Math.round((info.IER.faltantes / info.IER.listas) * 100) }}%</p>
  
  
  
  
  
        </div>
  
        <div class="info-container info-container4 bg-green-500 sm:w-1/2 rounded-md">
          <p v-if="info.IE">IE: Listas{{ info.IE.listas }}, faltantes {{ info.IE.faltantes }}</p>
          <img src="../assets/IE.png" alt=" " class="w-3/4 h-10 mx-auto  md:w-1/2 md:h-auto  mt-4 mb-4">
  
   
          <label v-if="info.IE">Porcentaje completado: {{ Math.round(((info.IE.listas - info.IE.faltantes) / info.IE.listas) * 100) }}%</label>
     <br>
     <div class="md:flex flex-row mb-5 mt-5">
          <label class="md:px-2">0%</label>
          <div class="bg-gray-300 w-full rounded-lg mt-1 ">
            <div v-if="info.IE" class="h-full bg-[#ff4444] rounded-lg" :style="{ width: `${Math.round(((info.IE.listas - info.IE.faltantes) / info.IE.listas) * 100)}%` }"></div>
         </div>
          <label class="md:px-2">100%</label>
        </div>
      <p v-if="info.IE" :style="{ color: (info.IE.faltantes === 0) ? 'green' : 'darkred' }"> Porcentaje Faltante: {{ Math.round((info.IE.faltantes / info.IE.listas) * 100) }}%</p>
  
  
  
  
        </div>
  
        <div class="info-container info-container5 bg-blue-500 sm:w-1/2 rounded-md">
          <p v-if="info.II">II: Listas{{ info.II.listas }}, faltantes {{ info.II.faltantes }}</p>
          <img src="../assets/II.png" alt=" " class="w-1/2 h-10 mx-auto  md:w-1/4 md:h-auto mt-2 mb-2">
  
          <label v-if="info.II">Porcentaje completado: {{ Math.round(((info.II.listas - info.II.faltantes) / info.II.listas) * 100) }}%</label>
     <br>
     <div class="md:flex flex-row mb-5 mt-5">
          <label class="md:px-2">0%</label>
          <div class="bg-gray-300 w-full rounded-lg mt-1 ">
            <div v-if="info.II" class="h-full bg-[#ff4444] rounded-lg" :style="{ width: `${Math.round(((info.II.listas - info.II.faltantes) / info.II.listas) * 100)}%` }"></div>
         </div>
          <label class="md:px-2">100%</label>
        </div>
      <p v-if="info.II" :style="{ color: (info.II.faltantes === 0) ? 'green' : 'darkred' }"> Porcentaje Faltante: {{ Math.round((info.II.faltantes / info.II.listas) * 100) }}%</p>
  
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue';
  
  const info = ref("");
  const isLoading = ref("");
  
  async function fetchData() {
    try {
      const response = await fetch('https:/sitmotul.com.mx/api/statusEvalIng');
      const data = await response.json();
      info.value = data;
      isLoading.value = false;
      console.log (data);
    }catch (error) {
      console.error('Error al obtener datos:', error);
    }
  }
  
  onMounted(() => {
    fetchData();
  });
  </script>