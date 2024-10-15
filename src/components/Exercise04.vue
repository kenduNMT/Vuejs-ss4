<template>
    <div>
        <label for="inputText">Nhập giá trị:</label>
        <input id="inputText" type="text" v-model="inputValue" />
    </div>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'

const inputValue = ref('')

watch(inputValue, (newValue, oldValue) => {
    console.log(`Giá trị thay đổi từ "${oldValue}" sang "${newValue}"`)
})
</script>

<style scoped>
label {
    font-size: 18px;
    font-weight: bold;
}

input {
    padding: 8px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin-top: 10px;
}
</style>