<template>
    <div>
        <p>Công ty: {{ info.company }}</p>
        <p>Tuổi: {{ info.age }}</p>
        <button @click="updateInfo">Thay đổi thông tin</button>
    </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const info = reactive({
    company: 'Rikkei Academy',
    age: 2
})

const updateInfo = () => {
    info.company = 'Rikkei Education'
    info.age = 1
}
</script>
button {
padding: 10px 20px;
font-size: 16px;
background-color: #007bff;
color: white;
border: none;
border-radius: 4px;
cursor: pointer;
}

button:hover {
background-color: #0056b3;
}

p {
font-size: 18px;
font-weight: bold;
}
<style scoped></style>