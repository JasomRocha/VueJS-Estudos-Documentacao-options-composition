<template>
<h1> Diretiva v-html</h1>
<!--  Se usarmos assim as tags Htmls serão apresentadas na tela-->
  <p>{{ elemento }}</p>
<!--  Nesse caso teremos de usar a diretiva v-html para interpretar as tags html-->
<!--  Então a diretiva irá basicamente aplicar o html no trecho de código da posição passada-->
  <p v-html="elemento"></p>
</template>

<script setup>
import {ref} from "vue";
// Deve haver muita cautela ao permitir que usuarios possam digitar htmls em campos de formulário etc.
// isso abre brechas para ataques XSS - ataque comum de injeção de html em tentativas de acesso indevido ao banco de dados
const elemento = ref('<b>Jasom</b>')
</script>

<style scoped>

</style>
