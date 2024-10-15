<template>
    <div>
        <p>Chiều dài (Width): {{ width }}</p>
        <p>Chiều cao (Height): {{ height }}</p>
        <p>Diện tích (Area): {{ area }}</p>
        <button @click="increaseWidth">Increase width</button>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const width = ref(10)
const height = ref(20)

const area = computed(() => width.value * height.value)

const increaseWidth = () => {
    width.value += 10
}
</script>

<style scoped>
button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #28a745;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

p {
    font-size: 18px;
    font-weight: bold;
}
</style>