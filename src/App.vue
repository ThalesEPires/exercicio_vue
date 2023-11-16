<script setup>
import { reactive } from 'vue';

  const estado = reactive({
    resultado: 0,
    valor1: 0,
    valor2: 0,
    operacao: '+'
  });

  function calcular() {
    const { valor1, valor2, operacao } = estado;

    switch (operacao) {
      case '+':
        estado.resultado = valor1 + valor2;
        break;
      case '-':
        estado.resultado = valor1 - valor2;
        break;
      case '*':
        estado.resultado = valor1 * valor2;
        break;
      case '/':
        estado.resultado = valor1 / valor2;
        break;
      default:
        estado.resultado = 0;
    }
  }
</script>

<template>
  <div class="container" >
      <input type="number" id="campo1" v-model="estado.valor1" @keyup="calcular" placeholder="Primeiro valor" required>
      <select class="operacao" v-model="estado.operacao" @change="calcular">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" id="campo2" v-model="estado.valor2" @keyup="calcular" placeholder="Segundo valor" required>
      <label class="resultado" for="resultado"> = {{ estado.resultado }}</label>
  </div>
</template>

<style scoped>
  .container {
    background-color: #ccc;
    padding: 12px;
    display: flex;
    margin-top: 16px;
    margin-left: 16px;
  }

  .operacao {
    margin: 0 16px;
    padding: 0 8px;
  }

  input[type="number"]::-webkit-outer-spin-button,
  input[type="number"]::-webkit-inner-spin-button {
    -webkit-appearance: none;
}

  .resultado {
    margin-left: 8px;
  }
</style>
