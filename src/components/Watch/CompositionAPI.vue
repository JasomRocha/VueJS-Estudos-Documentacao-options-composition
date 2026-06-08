<template>
<h1> Watch </h1>
  <label for="">Aceitar termos de uso</label>
  <input type="checkbox" v-model="terms">

  <p> {{ terms }} </p>
  <p> {{ status }}</p>
  <input type="submit" value="Submeter" :disabled />

</template>


<script setup>

import {ref, watch} from "vue";

const terms = ref( false);
const status = ref(null);
const disabled = ref(true);

watch(terms, () => {
  status.value = ' ';
  setTimeout(() => {
    disabled.value = false;
    status.value = 'Termos Aceitos! Obrigado. ' +
      'Pode seguir com a contratação so serviço';
  }, 3000)
})

</script>


<style scoped>

</style>
