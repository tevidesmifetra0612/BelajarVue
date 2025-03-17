<!-- src/App.vue -->
<script setup>
import profile from './components/profile.vue';
</script>

<template>
  <div class="container">
    <h1>Halaman Utama</h1>
    <profile /> 
  </div>
</template>

<style>
/* Background hitam untuk seluruh halaman */
body {
  background: black;
  color: white;
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}
</style>

<style scoped>
/* Container utama */
.container {
  text-align: center;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

/* Heading */
h1 {
  margin-bottom: 20px;
  font-size: 24px;
}
</style>
