<template>
  <h1> Diretiva v-if</h1>

<!--  As sentenças devem estar todas no mesmo nível-->
  <div v-if="user.is_admin === true">
    <p> Bem vindo, Administrador!</p>
  </div>

  <div v-else-if="user.is_active === true">
    <p> Bem vindo, Usuário!</p>
  </div>

  <div v-else>
    <p> Bem vindo, Usuário!</p>
  </div>

  <hr>
  <button @click="tab= 'manager'"> Gestão do aluno </button>
  <button @click="tab = 'enrollments'"> Matrículas </button>
  <button @click="tab= 'remove'"> Remover usuário </button>

  <div>
    <div v-if="tab === 'manager' ">
      <p> Gestão do aluno </p>
    </div>

    <div v-else-if="tab === 'enrollments' ">
      <Enrollments />
    </div>

    <div v-else>
      <p> Remover usuário </p>
    </div>
  </div>

</template>


<script setup>
import {reactive, ref} from "vue";
import Enrollments from "@/components/Directives/Enrollments.vue";

const user = reactive({
  is_admin: true,
  is_active: true
})

const tab = ref('manager')

</script>
