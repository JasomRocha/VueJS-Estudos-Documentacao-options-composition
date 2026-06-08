<template>
<h1>Composition API</h1>
  <p>O contador está no valor: {{ counter }}</p>
  <button @click="counter++">Somar</button>
</template>

<script setup>
import {
  onBeforeMount,
  onBeforeUnmount,
  onBeforeUpdate,
  onMounted,
  onUnmounted,
  onUpdated,
  ref
} from 'vue';

const counter = ref(0);

onBeforeMount(() => {
  console.log('1 - Before Mounted');
})

onMounted(() => {
  console.log('2 - on Mounted');
})

onBeforeUpdate(() => {
  console.log('3 - Before Update');
})

onUpdated(() => {
  console.log('4 - Updated');
})

onBeforeUnmount(() => {
  console.log('5 - Before Unmounted');
})

onUnmounted(() => {
  console.log('6 - on Unmounted');
})
</script>

<style scoped>

</style>
