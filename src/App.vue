<script setup>
import { reactive } from 'vue';

  const estado = reactive({
    resultado: 0,
    valor1: 0,
    valor2: 0
  })

  function somar() {
    const { valor1, valor2, resultado } = estado;
    return resultado = valor1 + valor2;
  }

  function subtrair() {
    const { valor1, valor2, resultado } = estado;
    return resultado = valor1 - valor2;
  }

  function multiplicar() {
    const { valor1, valor2, resultado } = estado;
    return resultado = valor1 * valor2;
  }

  function dividir() {
    const { valor1, valor2, resultado } = estado;
    return resultado = valor1 / valor2;
  }
</script>

<template>
  <div class="container" >
      <input type="number" id="campo1" @keyup="evento => estado.valor1 = evento.target.value" placeholder="Valor1" required>
      <select class="operacao">
        <option @click="somar">+</option>
        <option @click="subtrair">-</option>
        <option @click="multiplicar">*</option>
        <option @click="dividir">/</option>
      </select>
      <input type="number" id="campo2" @keyup="evento => estado.valor2 = evento.target.value" placeholder="Valor2" required>
      <label class="resultado" for="resultado"> = {{ estado.resultado }}</label>
  </div>
</template>

<style scoped>
  .container {
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
