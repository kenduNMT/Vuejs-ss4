<template>
    <div>
        <h1>Giỏ hàng</h1>

        <div v-for="(product, index) in products" :key="index" class="product">
            <p>{{ product.name }} - Số lượng: {{ product.quantity }}</p>
            <button @click="increaseQuantity(index)">Tăng số lượng</button>
        </div>

        <h2>Tổng số lượng sản phẩm trong giỏ: {{ totalQuantity }}</h2>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const products = ref([
    { name: 'Sản phẩm 1', quantity: 0 },
    { name: 'Sản phẩm 2', quantity: 0 },
    { name: 'Sản phẩm 3', quantity: 0 }
])

function increaseQuantity(index: number) {
    products.value[index].quantity++
}

const totalQuantity = computed(() => {
    return products.value.reduce((total, product) => total + product.quantity, 0)
})
</script>

<style scoped>
.product {
    margin-bottom: 10px;
}

button {
    background-color: #28a745;
    color: white;
    border: none;
    padding: 8px 12px;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

h1,
h2 {
    font-family: Arial, sans-serif;
}
</style>