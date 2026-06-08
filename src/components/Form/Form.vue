<template>
  <h1> Form </h1>
  <h2> Entendendo como os componentes comuns em formulários são alimentados pelo vue e monitorados por ele também</h2>
  <p>Um debugzinho do objeto formulário</p>
  <pre>
    {{ form }}
  </pre>
  <form>
    <label for="name">Nome do usuário: </label>
    <input type="text" id="name" v-model="form.name">

    <br /> <br />

    <label for="email">Email: </label>
    <input type="email" id="email" v-model="form.email">

    <br /> <br />

    <label for="texto">Texto: </label>
    <br /> <br />
    <textarea id="texto" v-model="form.bio"></textarea>
    <br /> <br />

    <label for="notification"> Deseja receber notificações? </label>
    <input type="checkbox" v-model="form.notification">
    <br /> <br />


    <p>Qual a sua habilidade? </p>
    <input type="radio" name="skill" value="backend" id="backend" v-model="form.skill">
    <label for="backend">Backend</label>

    <input type="radio" name="skill" value="frontend" id="frontend" v-model="form.skill">
    <label for="frontend">FrontEnd</label>

    <input type="radio" name="skill" value="fullstack" id="fullstack" v-model="form.skill">
    <label for="fullstack">FullStack</label>

    <br /> <br />

    <label for="skill_select">Qual é sua habilidade?</label>
    <br /> <br />
    <select name="skill_select" id="skill_select" v-model="form.skill_select" @change="mudaTexto">
      <option value="backend">Backend</option>
      <option value="frontend">FrontEnd</option>
      <option value="fullstack">Fullstack</option>
    </select>

    <br /> <br />

    <button type="submit" @click.prevent="submitForm">Enviar formulário</button>
  </form>

  <p ref="texto_resenha">{{ form.texto }}</p>

</template>

<script setup>
import {reactive, ref} from "vue";

// Criamos um objeto em memória do usuario, que pode ser passado como prop
// e podemos dizer se ele


// const props = defineProps({
//   user: {
//     type: Object,
//     required: true
//   }
// })

/**
 * Isso é semlhante à, no back end
 *
 * retornando uma blade com view, em laravel
 * $user = User::query()->where('email', 'jasom@teste.com')->first();
 * return view('user.edit', ['user' => $user] //blade
 *
 * ou ainda, se quiséssemos retornar um json
 * return response()->json($user) // json
 *
 * podemos usar o inertia para passar componentes vue diretamente para as engines do php/laravel
 * return Inertia::render('Form', ['user' => $user] // inertia
 */

// Simula os dados de um determinado usuário que veio do back end
  // preenchendo o formulário com as informações passada por um axios da vida etc
const props = {
  user: {
    name: 'Jasom Rocha',
    email: 'jasomrocha@teste.com',
    bio: 'Olá mundo!',
    notification: true,
    skill: 'backend',
    skill_select: 'fullstack'
  }
}

// O componente form possui uma propriedade (componente filho) user
// objeto local simulando uma prop
// que possui atributos name, email e bio
const form = reactive({
  name: props.user.name,
  email: props.user.email,
  bio: props.user.bio,
  notification: props.user.notification,
  skill: props.user.skill,
  skill_select: props.user.skill_select,
  texto: ''
})

const submitForm = function(){
  console.log('Formulário submetido!')
}


const texto_resenha = ref(null);
const mudaTexto = () => {
  if(form.skill_select === 'backend') {
    form.texto = "Ah você é o alecrim dourado dos código né?!"
    texto_resenha.value.style.color = 'red'
  } else if (form.skill_select === 'frontend') {
    form.texto = "Ah então você manja de centralizar divs, bacana!"
    texto_resenha.value.style.color = 'blue'
  } else if (form.skill_select === 'fullstack'){
    form.texto = "Hmm, então você é o bichão mesmo né? você fala e filma."
    texto_resenha.value.style.color = 'green'
  } else {
    form.texto = ''
  }
}

</script>

