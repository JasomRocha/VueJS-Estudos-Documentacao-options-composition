<template>
  <h1> Diretiva v-once </h1>
<!--A diretiva v-once só irá atualizar o componenete a primeira vez que ele for carregado-->
<!--  nesse caso abaixo de tivéssemos sem a diretiva ao clicar no botão ele mudaria o nome do usuario para 'Novo nome'-->
<!--  No entanto com a diretiva v-once depois que a view é montada você não consegue mais alterar o conteudo da posição-->
  <p v-once> O nome do usuário é {{ usuario.nome }}</p>
  <br>
  <button @click="usuario.nome= 'Novo nome'">Mudar nome</button>


</template>

<script setup>
import {reactive} from "vue";

const usuario = reactive({
  nome: 'Jasom'
})
</script>

<style scoped>

</style>
