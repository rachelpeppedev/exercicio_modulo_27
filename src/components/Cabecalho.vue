<script setup>
    const props = defineProps(['resultado'])
</script>
<template>
    <div class="container p-3 text-light bg-dark rounded-3">
        <header class="text-center">
            <h1>Calculadora Aritmética</h1>
            <div class="m-3 mx-5 bg-light text-dark ">
                <p class="m-0 text-uppercase">Resultado: {{ props.resultado }}</p>
            </div>
        </header>        
    </div>
</template>