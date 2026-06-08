<template>
  <h1> Bindings </h1>

  <label>Nome: </label>
  <input :type="input.type" :name="input.name">
  <label>Senha: </label>
  <input v-bind:type="pass.type" v-bind:name="pass.name"></input>
  <input type="button" value="Mostrar senha" @click="showHidePassword" />
</template>

<script setup>
import {reactive} from "vue";

const input = reactive({
  name: "name",
  type: "text",
  placeholder: "Digite seu nome aqui",
})

const pass = reactive({
  name: "password",
  type: "password",
})

const showHidePassword = function(){
  if(pass.type === "text"){
    pass.type = "password";
  } else {
    pass.type = "text";
  }
}
</script>

<style scoped>

</style>
