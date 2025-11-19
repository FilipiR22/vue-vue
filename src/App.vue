<template>
  <Navbar :caminho="caminho" :alt="alt" />
  <router-view />
  <Footer />
</template>
<script setup>
import { ref } from 'vue';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

const caminho = ref('/img/logo.png');
const alt = ref('Logo da Empresa');
</script>
<style>
* {
  font-family: Arial, Helvetica, sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
html,body{
  height: 100%;
}
.main-container {
  margin: 50px;
  min-height: 100%;
  flex-grow: 1;
}

h1 {
  text-align: center;
  font-size:42px;
  color: #222;
}
</style>