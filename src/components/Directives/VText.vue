<template>
  <h1> Diretiva v-text</h1>

  <p> O nome do usuario é {{ user }}</p>
<!--Uso comum da reatividade com o operador de interpolação double mustaches do vue-->
  <span>{{ user }}</span>

<!--  É basimente a mesma coisa do uso acima do double mustaches-->
  <span v-text="user"></span>
</template>

<script setup>

</script>

<style scoped>

</style>
