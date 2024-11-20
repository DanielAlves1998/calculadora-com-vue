<script setup>
import {ref} from 'vue'
const calculadoraValue = ref('')
const calculadoraElemento = ref(['C', '*', '/', '-', 7,8,9, '+', 4,5,6, '%', 1,2,3, '=', 0, '.'])
const operador = ref(null)
const preValue = ref('')

function action(ele) {

    if(!isNaN(ele) || ele === ".") {
        this.calculadoraValue += ele + ''
    }

    if(ele === "C") {
        this.calculadoraValue = ''
    }

    if(ele === '%'){
        this.calculadoraValue = this.calculadoraValue / 100;
    }

    if(['*', '/', '-', '+'].includes(ele)) {
        this.operador = ele
        this.preValue = this.calculadoraValue
        this.calculadoraValue = ''
    }

    if(ele === '='){
        this.calculadoraValue = eval(
            this.preValue + this.operador + this.calculadoraValue
        )
        this.operador = null
        this.preValue = ''
        
    }

}
</script>


<template>

    <div class="bg-[#234] max-w-[450px] p-6 mx-auto mt-5 shadow-md shadow-slate-800">

        <div class="w-full bg-slate-900 p-3 shadow-md shadow-slate-900 text-right text-white text-xl">
            {{ calculadoraValue || 0 }}
        </div>

        <div class="grid grid-cols-4 gap-3 mt-5">
            <div class="" v-for="ele in calculadoraElemento" :key="ele">
                <div class="p-5 bg-slate-800 hover:bg-slate-950 transition-all duration-200 cursor-pointer"
                :class="{'bg-green-500 hover:bg-green-700' : ['C', '*', '/', '-', '%', '+', '='].includes(ele)}"
                @click="action(ele)"
                >
                    {{ ele }}
                </div>
            </div>
        </div>

    </div>

</template>


<style scoped>
    

</style>