<script setup>
import { reactive } from 'vue'

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
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritimética</h1>
    </header>
    <form class="form">
      <div class="row">
        <div class="col-12">
          <select
            @change="(event) => (state.operacao = event.target.value)"
            class="form-control mb-4"
          >
            <option value="adicao">Adição</option>
            <option value="subitracao">Subitração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
        </div>
      </div>
      <div class="row">
        <div class="col-6">
          <input
            @keyup="state.num1 = $event.target.value"
            type="text"
            class="form-control"
            placeholder="Primeiro número"
          />
        </div>
        <div class="col-6">
          <input
            @keyup="state.num2 = $event.target.value"
            type="text"
            class="form-control"
            placeholder="Segundo número"
          />
        </div>
      </div>
    </form>
    <h2 class="text-center mt-4">O resultado é: {{ calcular() }}</h2>
  </div>
</template>
<style></style>
