<script setup>
    const props = defineProps(['num1', 'num2', 'result'])

</script>


<template>
    <span v-if="props.num1 && props.num2 !=''"><h2>Resultado: {{ props.result }}</h2></span>
    <span v-else-if="props.num1 || props2 === ''"><h2>digite dois números</h2></span>
</template>

<style>
span H2 {
    padding-bottom: 40PX;
}

</style>