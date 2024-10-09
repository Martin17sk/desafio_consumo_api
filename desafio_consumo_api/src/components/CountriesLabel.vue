<template>
    <div class="container">
        <h1>Countries API</h1>
        <p>{{ api_description }}</p>
        <p>{{ info }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue'

let api_description = ref('')
let info = ref('')

const getApiDescription = async () => {
    const response = await fetch('https://restcountries.com/v3.1/all')
    .then(response => {
        api_description.value = 'API description: ' + response.msg
    })
}
</script>

<style scoped>
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin-top: 50px;
    }
</style>