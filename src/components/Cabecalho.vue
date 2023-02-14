<script setup>
    const props = defineProps(['calcula'])
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-dark rounded-3">
        <h1 class="mb-5">Calculadora com Vue.js</h1>
        <h4> 
            A sua operação teve o resultado: <strong>{{ props.calcula }}</strong> 
        </h4>
    </header>
</template>