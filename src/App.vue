<template>
  <div>
    <h1>{{ mensagem }}</h1>

    <div class="contadorA">
      <p :class="classContadorA" >ContadorA: {{ contadorA }}</p>
      <button @click="incrementarA">Incrementar</button>
      <p> - </p>
      <button @click="decrementarA">Decrementar</button>
    </div>
    <hr>
    <div class="contadorB">
      <p :class="classContadorB">ContadorB: {{ contadorB }}</p>
      <button @click="incrementarB">+1</button>
      <p> - </p>
      <button @click="decrementarB">-1</button>
    </div>
  </div>
  <hr>
  <div class="total">
    <h2>Total: {{ total }}</h2>
  </div>
</template>

<script setup>
import { ref,computed } from 'vue'

const mensagem = ref('Hello, Vicente.js!')

const contadorA = ref(0)
const contadorB = ref(0)
const total = computed(() => contadorA.value + contadorB.value)
const classContadorA = computed(() => contadorA.value > contadorB.value ? 'destaque' : '')
const classContadorB = computed(() => contadorB.value > contadorA.value ? 'destaque' : '')

function incrementarA() {
  contadorA.value++  
}
function decrementarA() {
  contadorA.value--  
}
function incrementarB() {
  contadorB.value++  
}
function decrementarB() {
  contadorB.value--  
}

</script>

<style scoped>
h1 {
  color: #42b983;
  font-size: 2rem;
  text-align: center;
  margin-top: 50px;
}

.contador {
  margin-top: 20px;
  text-align: center;
}

button {
  padding: 5px 10px;
  font-size: 1rem;
  cursor: pointer;
}

.destaque {
  color: green;
  border: 2px solid green;
  border-radius: 10px;
  padding: 5px;
  font-weight: bold;
}
</style>