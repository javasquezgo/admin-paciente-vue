<script setup>
import { reactive } from "vue";

const paciente = reactive({
  mascota: "",
  propietario: "",
  email: "",
  alta: "",
  sintomas: "",
});

const validar = () => {
  console.log("Validando...");
};
</script>
<template>
  <div class="md:w-1/2">
    <h2 class="text-3xl font-black text-center">Seguimiento de pacientes</h2>
    <p class="mt-5 mb-10 text-lg text-center">
      Añade pacientes y
      <span class="font-bold text-indigo-600">Admínistralos</span>
    </p>

    <form
      class="px-5 py-10 mb-10 bg-white rounded-lg shadow-md"
      @submit.prevent="validar"
    >
      <div class="mb-5">
        <label class="block font-bold text-gray-700 uppercase" for="mascota"
          >Nombre de mascota</label
        >
        <input
          id="mascota"
          placeholder="Nombre de la mascota"
          class="w-full p-2 mt-2 placeholder-gray-400 border-2 rounded-m"
          type="text"
          v-model="paciente.mascota"
        />
      </div>

      <div class="mb-5">
        <label class="block font-bold text-gray-700 uppercase" for="propietario"
          >Nombre de Propietario</label
        >
        <input
          id="propietario"
          placeholder="Nombre del propietario"
          class="w-full p-2 mt-2 placeholder-gray-400 border-2 rounded-m"
          type="text"
          v-model="paciente.propietario"
        />
      </div>

      <div class="mb-5">
        <label class="block font-bold text-gray-700 uppercase" for="email"
          >Email</label
        >
        <input
          id="email"
          placeholder="Email del propietario"
          class="w-full p-2 mt-2 placeholder-gray-400 border-2 rounded-m"
          type="email"
          v-model="paciente.email"
        />
      </div>

      <div class="mb-5">
        <label class="block font-bold text-gray-700 uppercase" for="alta"
          >Fecha de alta</label
        >
        <input
          id="alta"
          placeholder="Fecha de alta"
          class="w-full p-2 mt-2 placeholder-gray-400 border-2 rounded-m"
          type="date"
          v-model="paciente.alta"
        />
      </div>

      <div class="mb-5">
        <label class="block font-bold text-gray-700 uppercase" for="sintomas"
          >Sintomas</label
        >
        <textarea
          name="sintomas"
          id="sintomas"
          placeholder="Síntomas"
          class="w-full h-40 p-2 mt-2 placeholder-gray-400 border-2 rounded-md"
          cols="30"
          rows="10"
          v-model="paciente.sintomas"
        ></textarea>
      </div>

      <input
        type="submit"
        class="w-full p-3 font-bold text-white uppercase transition-colors bg-indigo-600 cursor-pointer hover:bg-indigo-700"
        value="Registrar paciente"
      />
    </form>
  </div>
</template>