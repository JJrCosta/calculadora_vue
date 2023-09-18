<script setup>
import { reactive } from 'vue';

const state = reactive({
    valor1: '',
    valor2: '',
    operador: 'soma'
});

const result = () => {
    let valor1 = state.valor1;
    let valor2 = state.valor2;
    
    if (valor1 < valor2) {
        return 'Erro'
    }
    
    switch (state.operador) {
        case 'soma':
            return valor1 + valor2;
        case 'subtracao':
            return valor1 - valor2;
        case 'multiplicacao':
        return valor1 * valor2;
        case 'divisao':
            if ((valor1 % valor2) === 0) {
                return valor1 / valor2;
            } else {
                return (valor1 / valor2).toFixed(2)
            }
        case '':
            return '';
    }
};
</script>

<template>
    <div class="container mx-auto">
        <header class="p-5 my-4 bg-dark rounded-3">
        <h1 class="text-center fw-bold text-light">Calculadora Vue.JS</h1>
        </header>

        <div class="row">
        <div class="col">
            <h4 class="text-center">Selecione a operação e informe os valores</h4>
            <form class="bg-dark p-2">
            <input class="form-control ps-2 me-md-3 my-3" type="number" placeholder="Informe o valor" v-model="state.valor1">
            <select class="form-control bg-primary text-light" v-model="state.operador">
                <option value="soma">Adição</option>
                <option value="subtracao">Subtração</option>
                <option value="multiplicacao">Multiplicação</option>
                <option value="divisao">Divisão</option>
            </select>
            <input class="form-control ps-2 my-3" type="number" placeholder="Informe o valor" v-model="state.valor2">
            </form>
        </div>
        </div>
        <div class="row">
        <div class="col">
            <span class="result_container text-center fs-2 mt-2 p-3 border d-block">
            Resultado:
            <br>
            <span class="resultado">
                {{ result() }}
            </span>
            </span>
        </div>
        </div>
    </div>
</template>

<style scoped>
    @font-face {
        font-family: calculator;
        src: url('./assets/font/Calculator.ttf') format('truetype');
    }
    .container {
        max-width: 768px;
        width: 100%;
    }
    .resultado,
    h1 {
        font-size: 3em;
        letter-spacing: 2px;
        font-family: 'calculator', monospace;
    }
    .result_container {
        height: 195px;
    }
</style>