<template>
  <h1>v-model</h1>

  <form @submit.prevent="submitForm">
    <label for="">Nome: </label>
    <input name="name" type="text" v-model="form.name" />

    <label for="">Email: </label>
    <input name="email" type="email" v-model="form.email" />

    <button type="submit">Enviar</button>
  </form>

</template>

<script setup>

import {reactive} from 'vue';

const form = reactive({
  name: 'Jasom Rocha',
  email: ''
})

const submitForm = function (){
  console.log(form.name, form.email);
}
</script>

<style scoped>

</style>
