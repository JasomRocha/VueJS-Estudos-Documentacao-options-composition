<template>
  <h1>Reactive Example</h1>
  <p>Contador: {{ form.counter }}</p>

  <button  @click="sumCounter">Somar</button>
  <button @click="subCounter">Subtrair</button>
</template>

<script setup>
import {reactive} from 'vue';

const form = reactive({
  counter: 0
});

const sumCounter = function(){
  form.counter += 1;
}

const subCounter = function(){
  form.counter -= 1;
}
</script>

<style scoped>

</style>
