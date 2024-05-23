<script setup>
import { ref } from 'vue';

const dias = ref([
  {
    day: "Lunes",
    menu: {
      desayuno: "Desayuno Lunes",
      almuerzo: "Almuerzo Lunes",
      cena: "Cena Lunes",
    },
    estado: false,
  },
  {
    day: "Martes",
    menu: {
      desayuno: "Desayuno Martes",
      almuerzo: "Almuerzo Martes",
      cena: "Cena Martes",
    },
    estado: false,
  },
  {
    day: "Miércoles",
    menu: {
      desayuno: "Arepa rellena",
      almuerzo: "Caldo de Carne",
      cena: "Empanada",
    },
    estado: true,
  },
  {
    day: "Jueves",
    menu: {
      desayuno: "Desayuno Jueves",
      almuerzo: "Almuerzo Jueves",
      cena: "Cena Jueves",
    },
    estado: false,
  },
  {
    day: "Viernes",
    menu: {
      desayuno: "Desayuno Viernes",
      almuerzo: "Almuerzo Viernes",
      cena: "Cena Viernes",
    },
    estado: false,
  },
  {
    day: "Sábado",
    menu: {
      desayuno: "Desayuno Sábado",
      almuerzo: "Almuerzo Sábado",
      cena: "Cena Sábado",
    },
    estado: false,
  },
]);

const selectedDay = ref(null);

const selectDay = (index) => {
  selectedDay.value = index;
};
</script>
<template>
    <div class="justify-center mt-12 flex bg-red-200">
      <div class="bg-violet-200 p-3">
        <div class="flex bg-blue-600 p-3" v-for="(dia, i) in dias" :key="i">
          <div :class="['mb-2 py-3 px-2 justify-between w-80 flex select-none cursor-pointer hover:bg-slate-300', selectedDay === i ? 'bg-blue-400' : 'bg-slate-400' ]"          
            @click="selectDay(i)"  
          >
            {{ dia.day }}
          </div>
        </div>
      </div>
    
      <div class="bg-blue-400 mb-2">
        <div v-if="selectedDay !== null">
          <div class="px-4 mx-12 mt-4">
            <p><strong>Desayuno:</strong> {{ dias[selectedDay].menu.desayuno }}</p>
            <p><strong>Almuerzo:</strong> {{ dias[selectedDay].menu.almuerzo }}</p>
            <p><strong>Cena:</strong> {{ dias[selectedDay].menu.cena }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  