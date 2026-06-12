
<template>
 <h1> Título do meu card: {{ props.title}}</h1>
  <p> Saída do form.title: {{ form.title }}</p>
  <input type="text" v-model="form.title" />

  <p> Corpo do meu card: {{ props.body }}</p>

  <p> Quantidade de acessos: {{ props.access }}</p>

  <p> status: {{ props.status }} </p>
</template>

<script setup>
// Uso mais básico das props (Não recomendada)
// const props = defineProps([
//     'title', 'body', 'access', 'status'
// ])

// const props = defineProps({
//   title: String,
//   body: String,
//   access: Number,
//   status: Boolean
// })

// Além de declarar as props já conseguimos definir valores padrão e gerar validações
// Essa forma é a mais utilizada
// const props = defineProps({
//   title: {
//     type: String,
//     required: true
//   },
//   body:{
//     type: String,
//     default: 'Valor Padrão'
//   },
//   access: {
//     type: Number || String, // pode ser assim também [Number, String]
//     default: 0
//   },
//   status: {
//     type: Boolean,
//     required: true
//   }
// })

import {reactive} from "vue";

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  body:{
    type: String,
    default: 'Valor Padrão'
  },
  access: {
    type: Number || String, // pode ser assim também [Number, String]
    default: 0
  },
  status: {
    type: Boolean,
    required: true
  },
  format: {
    type: String,
    required: true,
    validator(value){
      return ['post', 'user'].includes(value)
    }
  }
})

const form = reactive({
  title: props.title
})
</script>

<style scoped>

</style>
