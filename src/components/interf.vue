<script setup>
import api from './api.vue';
import api2 from './api2.vue';


</script>

<template>

 <div class="text-center">
 
    <p class="text-blue-500 text-xl md:text-5xl text-center "> Sistema Institucional de Tutoría del ITS Motul</p>                      

    
<img src="../assets/logo1.png" alt="logotipo del sitmotul" class="w-70 h-40 mx-auto mt-4">
<div class="flex flex-row">

  <div class="flex flex-col w- md:p-5 ">
    <api> </api>
  </div>
  <div class="flex flex-col md:p-5">
    <api2></api2>
  
  </div>
  <br>

</div>
<div class="mt-auto px-6 py-6">
    <div class="w-full mx-auto bg-white px-10 py-3 text-center shadow-md">
        <p><span class=" text-3xl md:text-5xl font-bold">50 h</span><br> para finalizar</p></div>

        <div class="flex flex-col md:flex-row gap-5">
    <div class="flex-1 container mx-auto bg-red-800 rounded-lg text-sky-200 px-5 md:px-10 py-8 shadow-md">
        <div class="flex flex-col md:flex-row gap-2 md:gap-5 items-center justify-center mb-2">
        <h3 class=" text-white text-3xl md:text-5xl font-bold">28 %</h3>
        </div>
        <p class=" text-white text-center">230 faltantes</p>
    </div>
</div>
  </div>
</div>




</template>








