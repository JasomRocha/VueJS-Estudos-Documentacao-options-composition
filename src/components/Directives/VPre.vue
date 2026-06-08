<template>
  <h1> Diretiva v-pre</h1>

  <p> O nome do usuario é: {{ user }}</p>
  <p v-pre> O nome do usuario é: {{ user }}</p>
</template>

<script setup>
import {ref} from "vue";

const user = ref('Jasom')
</script>
