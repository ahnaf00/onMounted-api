<script setup>
import { ref, onBeforeMount, onMounted } from 'vue';

const apiResponse = ref(null);

onMounted(() => {
    fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then((response) => response.json())
        .then((data) => {
            apiResponse.value = data;
        });
});

</script>

<template>
    <div class="my-5 fs-4">{{ apiResponse }}</div>
    <div class="text-start fs-3" v-for="(value, key, index) in apiResponse" :key="index">
        {{ key }}: {{ value }}
    </div>
</template>

<style scoped></style>