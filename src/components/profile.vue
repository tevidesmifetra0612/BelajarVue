<!-- src/components/Profil.vue -->
<script setup>
import { ref } from 'vue';

const name = ref('Eliza');
const age = ref(25);

const rename = () => {
  nama.value = 'Eliza';
};

const Addage = () => {
  umur.value++;
};
</script>

<template>
  <div class="profil-container">
    <h2>Profil Pengguna</h2>

    <label>name:</label>
    <input v-model="name" type="text" />

    <label>age:</label>
    <input v-model="age" type="number" min="0" />

    <button @click="rename">Ubah Nama</button>
    <button @click="Addage">Tambah Umur</button>

    <p>Nama: {{ name }}</p>
    <p>Umur: {{ age }} tahun</p>
  </div>
</template>

<style scoped>
/* Container Profil */
.profil-container {
  max-width: 300px;
  margin: 20px auto;
  padding: 15px;
  background: #222;
  border-radius: 8px;
  text-align: center;
  color: white;
}

/* Input */
input {
  width: 100%;
  padding: 5px;
  margin: 5px 0;
  border: none;
  border-radius: 4px;
  background: #333;
  color: white;
}

/* Button */
button {
  margin: 5px;
  padding: 8px;
  border: none;
  border-radius: 4px;
  background: #007bff;
  color: white;
  cursor: pointer;
}

button:hover {
  background: #0056b3;
}
</style>
