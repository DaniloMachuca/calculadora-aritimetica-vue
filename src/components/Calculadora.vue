<script setup>
const props = defineProps(['num1', 'num2', 'trocarOperacao'])
</script>

<template>
  <form class="form">
    <div class="row">
      <div class="col-12">
        <select @change="props.trocarOperacao" class="form-control mb-4">
          <option value="adicao">Adição</option>
          <option value="subitracao">Subitração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>
      </div>
    </div>
    <div class="row">
      <div class="col-6">
        <input @keyup="props.num1" type="text" class="form-control" placeholder="Primeiro número" />
      </div>
      <div class="col-6">
        <input @keyup="props.num2" type="text" class="form-control" placeholder="Segundo número" />
      </div>
    </div>
  </form>
</template>
