<script setup>
    const props = defineProps(['resultado']);
</script>

<template>
    <div class="container p-3 text-light bg-dark rounded-3">
        <header class="text-center">
            <h1>Calculadora Aritmética</h1>
            <div class="m-3 mx-5 bg-light text-dark ">
                <p class="m-0 text-uppercase">Resultado: {{ resultado }}</p>
            </div>
        </header>        
    </div>
</template>

<style scoped>
.container {
    max-width: 600px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }
    </style>