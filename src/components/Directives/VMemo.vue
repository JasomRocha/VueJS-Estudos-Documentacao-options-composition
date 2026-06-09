<template>
<h1>Diretiva V-Memo</h1>

<div>
  <p>[puro] - O contador está em {{ counter}}</p>
  <button @click="counter++">Somar</button>
</div>
  <br>
<div>
  <p v-once>[v-once] - O contador está em {{ counterVOnce}}</p>
  <span>Renderizou um vez não sofre mais atualizações</span>
  <br>
  <button @click="counterVOnce++">Somar</button>
</div>

  <br>
<div>
  <p v-memo="[counterVMemo]">[v-memo] - O contador está em {{ counterVMemo }}</p>
  <span>Recebe um vetor que possui os nós específicos que sofem alterações naquele componente e precisam ser monitorados</span>
  <br>
  <button @click="counterVMemo++">Somar</button>
</div>


</template>

<script setup>
import {ref} from "vue";

const counter = ref(0)
const counterVOnce = ref(0)
const counterVMemo = ref(0)
</script>

<style scoped>

</style>
