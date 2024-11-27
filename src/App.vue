<script setup>
import {ref} from 'vue'

const campo1 = ref('')



</script>


<template>
<div class="container pt-1 mb-4 mt-4 bg-light rounded-3">
    

    <div id="campo1">
        <h3>Primeiro Número</h3>
        <input type="number" placeholder="digite o segundo número">
        
    </div>
    
    <div id="campo2">
        <h3>Segundo Número</h3>
        <input type="number" placeholder="digite o segundo número">
    </div>
    
    <div id="operacoes" class="col-7">
        <select class="form-control">
        <option value="divisao">divisão (/)</option>
        <option value="multiplicacao">multiplicação (*)</option>
        <option value="adicao">adição (+)</option>
        <option value="subtracao">subtração (-)</option>
        <option value="porcentagem">porcentagem (%)</option>
    </select>
    </div>

</div>
</template>




<style scoped>
h1 {
    text-align: center;
    margin-top:200px ;
}

#campo1 {
    text-align: center;
    padding-top: 70px;
    padding-bottom: 70px ;
}
#campo2 {
    text-align: center;
}
input {
    background-color: aliceblue;
    color: black;
}
#operacoes {
    font-family: 'Courier New', Courier, monospace;
    padding-top: 60px;
    
    padding-bottom: 90px;
    padding-left: 350px;
}

</style>
