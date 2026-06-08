<template>
<h1>Diretiva v-for</h1>

  <table>
    <tr>
      <td>ID</td>
      <td>Nome</td>
      <td>Email</td>
    </tr>

    <tr v-for="user in users" :key="user.id">
      <td>{{ user.id }}</td>
      <td>{{ user.name }}</td>
      <td>{{ user.email }}</td>
    </tr>
  </table>

  <select name="contact" v-model="form.contactForm">
    <option v-for="(type, index) in contactType" :key="index" :value="type.value">{{ index }} - {{ type.label }}</option>
  </select>

  {{ form }}
</template>

<script setup>
import {reactive} from "vue";

const users = [
  {
    id: 1,
    name: 'Jasom',
    email: 'jasom@teste.com'
  },
  {
    id: 2,
    name: 'Joao Rocha',
    email: 'contato1@blackdev.com'
  },
  {
    id: 3,
    name: 'Jose costa',
    email: 'contato2@blackdev.com'
  },
  {
    id: 4,
    name: 'Joana Rocha',
    email: 'contato3@blackdev.com'
  },
  {
    id: 5,
    name: 'Gustavo web',
    email: 'contato5@blackdev.com'
  },
]

const contactType = [
  {
    value: 'contact',
    label: 'Contato'
  },
  {
    value: 'without_connection',
    label: 'Sem conexão com a internet'
  },
  {
    value: 'internet_slow',
    label: 'Lentidão da internet'
  }
]

const form = reactive({
  contactForm: ''
})

</script>

