<template>
    <div>
        <h1>Giỏ hàng 2</h1>

        <input v-model.number="inputValue" type="number" />

        <button @click="addToCart">Add to cart</button>

        <h2>Tổng tiền trong giỏ hàng: {{ totalPrice }}</h2>
    </div>
</template>

<script setup lang="ts">
import { ref, computed, watch } from 'vue'

const inputValue = ref(0)

const totalAmount = ref(0)

function addToCart() {
    totalAmount.value += inputValue.value
    inputValue.value = 0
}

const totalPrice = computed(() => totalAmount.value)

watch(inputValue, (newValue, oldValue) => {
    console.log(`Giá trị đã thay đổi từ ${oldValue} sang ${newValue}`)
})
</script>

<style scoped>
input {
    margin-right: 10px;
    padding: 5px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
    border-radius: 4px;
}

button:hover {
    background-color: #0056b3;
}

h1,
h2 {
    font-family: Arial, sans-serif;
}
</style>