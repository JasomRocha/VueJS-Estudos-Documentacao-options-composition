<template>
<h1> Diretiva v-show </h1>
<!--o v-if aparece comentado no DOM, e não com display none-->
  <div v-if="test">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore laborum tempora ut.</p>
    <p>Illum mollitia obcaecati, pariatur quisquam quos saepe sed sit tenetur? Aperiam at doloribus ex illo magnam quibusdam sint.</p>
  </div>
<!--  o v-show é colocado no DOM com um display: none-->
  <div v-show="test">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore laborum tempora ut.</p>
    <p>Illum mollitia obcaecati, pariatur quisquam quos saepe sed sit tenetur? Aperiam at doloribus ex illo magnam quibusdam sint.</p>
  </div>
</template>

<script setup>
  import {ref} from "vue";

  const test = ref(true);
</script>

<style scoped>

</style>
