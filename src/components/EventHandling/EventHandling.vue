<template>
  <h1> Event Handling</h1>
<!--  <input type="text" :onclick="myFunc">-->
<!--  Utilizando o v-on você tem recursos a mais para explorar -->
<!--  <input type="text" v-on:click.prevent="myFunc">-->
  <!--  Você ainda pode utilizar o atalho @ ( siginifica v-on) são shorthands  como os : para o v-bind-->
<!--  <input type="text" @click.prevent="myFunc">-->

<!--Você previne o comportamento padrão do submit que seria eenviar o formulário para a url -->
<!--porque usamos a diretiva do JS prevent que captura o evento que foi de submissão   -->
<!--No entanto não permite a execução do disparo do formulário, fazendo com que a execução do codigo pare-->
<!--Logo após o submitForm (função propietária ser executada  -->
<!--@submit.prevent: intercepta o submit antes de enviar para a action URL.-->
<!--O .prevent chama preventDefault(), bloqueando o redirecionamento-->
<!--e permitindo que submitForm() trate os dados via JS.-->

  <form action="https://www.google.com.br" @submit.prevent="submitForm">
    <label>Nome: </label>
    <input type="text" name="name" v-model="form.name" />

    <label>E-mail: </label>
    <input type="email" name="email" v-model="form.email">

    <button type="submit" >Enviar Formulário </button>
  </form>
</template>

<script setup>

import {reactive} from "vue";

const form = reactive({
  name: "Jasom Rocha",
  email: "jasomrocha@teste.com.br",
})

/**
 * Executada no submit do form.
 * O .prevent no @submit garante que esta função rode
 * no lugar do comportamento padrão (redirecionar para a action).
 */
const submitForm = function() {
  console.log(form.name, form.email);
  console.log('Código finalizado com sucesso')
}

// const myFunc = function () {
//   console.log("Hello World!")
// }

</script>

<style scoped>

</style>
