<script setup>
import { ref } from 'vue'

let inputPutin = ref('')
let onixan = ref(0)
let codigos1 = ref([
  ['H6XDLW', '7WLOP7Y', 'POI834AX', '3XDLWUX'],
  ['XDA2LWX','ASDAD34A', 'ASDA4RG'],['ASDAD6XD', 'ASD3E4D', 'ASD354XA']
])

function addCode(onixan) {
  codigos1.value[onixan].push(inputPutin.value)
}

function sumatoria(){

  

}
</script>

<template>
  <div class="max-w-xl container">
    <div class="text-center text-xl font-bold">SISTEMA DE TURNOS</div>

    <div class="flex justify-between mt-8 mx-auto">
      <div>
        <div class="bg-blue-400 p-2 rounded-md text-white w-40 text-center mb-1">MODULO 1</div>
        <div class="bg-gray-300 rounded-md p-2">
          <div v-for="(obj, index) in codigos1[0]" :key="index">
            {{ obj }}
          </div>
        </div>
      </div>

      <div>
        <div class="bg-green-500 p-2 rounded-md text-white w-40 text-center">MODULO 2</div>
        <div class="bg-gray-300 rounded-md p-2 mt-1">
          <div v-for="(obj, index) in codigos1[1]" :key="index">{{ obj }}</div>
        </div>
      </div>
  
    <div>
      <div class="bg-orange-500 p-2 rounded-md text-white w-40 text-center">MODULO 3</div>
      <div class="bg-gray-300 rounded-md p-2 mt-1">
        <div v-for="(obj, index) in codigos1[2]" :key="index">
          {{ obj }}
        </div>
      </div>
    </div>
    </div>
  </div>

  <div class="bg-gray-300 rounded-lg max-w-xl mt-2 flex justify-between p-4">
    <div><h1 class="text-xl font-bold">{{ sumatoria() }}</h1></div>
    <div>
      <input
        v-model="inputPutin"
        class="w-28 rounded-md h-7 p-2"
        type="text"
        placeholder="CODIGO"
      />
    </div>

    <div>

      <div> <input v-model="onixan" class="rounded-md w-32 h-6 p-1" type="number" placeholder="Ingresa modulo"></div>

    </div>
    <div @click="addCode(onixan)" class="bg-violet-600 text-white rounded-md w-32 h-10 p-2 text-center">
      Agregar turno
    </div>
  </div>
</template>
