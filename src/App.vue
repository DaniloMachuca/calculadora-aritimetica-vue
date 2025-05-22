<script setup>
import { reactive } from 'vue'
import Titulo from './components/Titulo.vue'
import Calculadora from './components/Calculadora.vue'
import Visor from './components/Visor.vue'

const state = reactive({
  num1: 0,
  num2: 0,
  resultado: 0,
  operacao: 'adicao',
})

function calcular() {
  switch (state.operacao) {
    case 'adicao':
      state.resultado = parseInt(state.num1) + parseInt(state.num2)
      return state.resultado
    case 'subitracao':
      state.resultado = state.num1 - state.num2
      return state.resultado
    case 'multiplicacao':
      state.resultado = state.num1 * state.num2
      return state.resultado
    case 'divisao':
      state.resultado = state.num1 / state.num2
      return state.resultado
  }
}
</script>
<template>
  <div class="container">
    <Titulo />
    <Calculadora
      :num1="(event) => (state.num1 = event.target.value)"
      :num2="(event) => (state.num2 = event.target.value)"
      :trocar-operacao="(event) => (state.operacao = event.target.value)"
    />
    <Visor :resultado="calcular()" />
  </div>
</template>
<style></style>
