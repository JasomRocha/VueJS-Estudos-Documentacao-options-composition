<template>
  <h1> Watch </h1>
  <label for="">Aceitar termos de uso</label>
  <input type="checkbox" v-model="form.terms">

  <p> {{ terms }} </p>
  <p> {{ status }}</p>
  <input type="submit" value="Submeter" :disabled />

</template>


<script setup>

import {reactive, ref, watch} from "vue";

const form = reactive({
  terms: false,
});
const status = ref(null);
const disabled = ref(true);

// 1 - Se passarmos o 'form' ele se tornará um deep watch
// um observador profundo do meu formulário, difernt de monitorar
// apenas a posição terms como 'ref'
// o problema é que quando qualquer posição que mudar dentro do form
// eele irá executar o comportamento indesejadamente
    // watch(() => form.terms, () => {
    //   status.value = ' ';
    //   setTimeout(() => {
    //     disabled.value = false;
    //     status.value = 'Termos Aceitos! Obrigado. ' +
    //       'Pode seguir com a contratação so serviço';
    //   }, 3000)
    // })
// 2 - Se passarmos form.terms o vue ainda irá reclamar pois
// uma posição dentro de um objeto não é exatamente o que ele espera

    // watch(() => form.terms, () => {
    //   status.value = ' ';
    //   setTimeout(() => {
    //     disabled.value = false;
    //     status.value = 'Termos Aceitos! Obrigado. ' +
    //       'Pode seguir com a contratação so serviço';
    //   }, 3000)
    // })

// então devemos retornar essa posição como o resultado de uma função para que ele
// entenda que aquela posição é de fato reativa, como no exemplo abaixo
watch(() => form.terms, () => {
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
