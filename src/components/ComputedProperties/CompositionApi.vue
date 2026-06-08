<template>
 <h1>Computed Properties</h1>

  <input type="text" v-model="userFullName" >
  <p>O nome completo do usuário é: {{ user.firstName }} {{ user.lastName }} </p>
  <p>O nome completo do usuário é: {{ userFullName }} </p>

  <p>O valor do pedido é: {{ orderPriceFormated }}</p>
</template>

<script setup>

import {computed, reactive} from "vue";

// tudo sobre usuário
// Propriedade reativa
const user = reactive({
  firstName: "Jasom",
  lastName: 'Web',
})

// apenas lendo uma propriedade computada
// const userFullName = computed( () =>{
//     return user.firstName + " " + user.lastName
// });

// propridade computada que acessa e processa uma propriedad reativa
// atualizando o valor
// writable computed properties
const userFullName = computed( {
    get(){
      return user.firstName + " " + user.lastName
    },
    set(newValue){
      user.firstName = newValue.split(' ')[0];
      user.lastName = newValue.split(' ')[1];
    }
});

// Tudo sobre monetário
const order = reactive({
  price: 99700
})

const formatCurrency = new Intl.NumberFormat('pt-BR', {
  style: 'currency',
  currency: 'BRL',
  minimumFractionDigits: 2
})

const orderPriceFormated = computed( () => {
  return formatCurrency.format( order.price / 100)
})
</script>




