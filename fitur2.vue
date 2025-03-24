<script setup>
import { ref, computed, onMounted, nextTick } from 'vue';

let id = 0;
const newbook = ref('');
const books = ref([
    { id: 1, name: "dasar-dasar pemrograman", done: true },
    { id: 2, name: "Kisah Sang Rasul", done: false },
    { id: 3, name: "pendidikan pancasila", done: true }
]);

const completebook = computed(() => books.value.filter(book => book.done).length);
const jumlahbook = computed(() => books.value.length);

const inputRef = ref(null); // Template ref untuk input

function addbook() {
    if (newbook.value.trim()) {
        books.value.push({ id: id++, name: newbook.value, done: false });
        newbook.value = '';

        // Gunakan nextTick agar memastikan DOM diperbarui sebelum memberi fokus kembali ke input
        nextTick(() => {
            inputRef.value.focus();
        });
    }
}

function removebook(book) {
    books.value = books.value.filter((b) => b !== book);
}

// Lifecycle hook: saat komponen dimuat, beri fokus ke input
onMounted(() => {
    inputRef.value.focus();
});
</script>

<template>
    <form @submit.prevent="addbook">
        <input ref="inputRef" v-model="newbook" required placeholder="New book">
        <button> Add Book</button>
    </form>
    <p>Jumlah buku selesai: {{ completebook }}</p>
    <p>Total buku: {{ jumlahbook }}</p>
    <ul>
        <li v-for="book in books" :key="book.id">
            <input type="checkbox" v-model="book.done">
            <span :class="{ done: book.done }">{{ book.name }}</span>
            <button @click="removebook(book)">X</button>
        </li>
    </ul>
</template>

<style>
.done {
    text-decoration: line-through;
}
</style>
