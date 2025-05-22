<script setup>
const props = defineProps(['resultado'])
</script>

<template>
  <h2 class="text-center mt-4">O resultado é: {{ props.resultado }}</h2>
</template>
