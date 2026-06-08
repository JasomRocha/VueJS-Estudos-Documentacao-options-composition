<template>
 <h1>Template Ref</h1>
<!--  Transforma o componente html em um componente que o vue possa gerenciar propriedades-->
  <p id="welcome" ref="welcome">Hello world!</p>
</template>

<script setup>
import {onMounted, ref} from "vue";

console.log('start na naplicação');

const welcome = ref(null);

// Espero o elemento ser montado no DOM
// e agora posso acesssar as propriedades daquele elemento na tela
onMounted(() => {
  //const teste = document.querySelector("#welcome");
  welcome.value.style.color = 'red';
  console.log(teste);
})

</script>

<style scoped>

</style>
