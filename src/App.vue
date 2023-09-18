<script setup>

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
              <input class="form-control ps-2 me-md-3 my-3" type="number" placeholder="Informe o valor" required>
              <select class="form-control bg-primary text-light">
                  <option value="+">Adição</option>
                  <option value="-">Subtração</option>
                  <option value="*">Multiplicação</option>
                  <option value="/">Divisão</option>
              </select>
              <input class="form-control ps-2 my-3" type="number" placeholder="Informe o valor" require>
            </form>
        </div>
    </div>
    <div class="row">
        <div class="col">
            <span class="text-center fs-2 mt-2 p-3 border d-block">
                Resultado:
                <br>
                <span class="resultado">
                    00
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
</style>