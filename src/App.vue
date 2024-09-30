<script setup>
import { reactive, computed } from 'vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
  operacao: 'soma',
});

const calcularResultado = computed(() => {
  const { numero1, numero2, operacao } = estado;
  switch (operacao) {
    case 'soma':
      return numero1 + numero2;
    case 'subtracao':
      return numero1 - numero2;
    case 'multiplicacao':
      return numero1 * numero2;
    case 'divisao':
      return numero2 !== 0 ? numero1 / numero2 : 'Divisão por zero!';
    default:
      return 0;
  }
});
</script>

<template>
  <div class="container calculadora mt-5">
    <h1 class="text-center mb-4">Calculadora Aritmética</h1>
    <div class="card p-4 shadow">
      <Formulario :estado="estado" />
      <Resultado :resultado="calcularResultado" />
    </div>
  </div>
</template>

<style scoped>
.calculadora {
  max-width: 600px;
  margin: 0 auto;
}

h1 {
  font-family: 'Arial', sans-serif;
  color: #2c3e50;
  font-weight: bold;
}

.card {
  background-color: #f8f9fa;
  border-radius: 10px;
  border: none;
}
</style>
