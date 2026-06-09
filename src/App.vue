<script>
import VPre from "./components/Directives/VPre.vue";
import VOnce from "./components/Directives/VOnce.vue";
import VMemo from "./components/Directives/VMemo.vue";

// Quando retiramos o setup do script, ele importa como se fosse options API
// A maneira como ele importa é diferente da maneira como é feito no compositions API
// import {defineComponent} from "vue";
// import Options from "./components/Register/Options.vue";
//
// export default defineComponent({
//   components: {Options}
// })

// Você pode dar um ALIAS para o seu componente se julgar necessário (aplicação legada faz isso)
import {defineComponent} from "vue";
import Options from "./components/Register/Options.vue";

export default defineComponent({
  components: {
    MeuComponenteA: Options
  }

})

</script>


<template>
<!--  <options-api />-->
<!--  <RefExample />-->
<!--  <ReactiveExample />-->
<!--<v-model-example />-->
<!--  <CompositionAPI />-->
<!--  <TemplateRef/>-->
<!--  <Bindings/>-->
<!--  <EventHandling />-->
<!--<Form />-->
<!--  <VIf />-->
<!-- <VShow />-->
<!-- <VText />-->
<!-- <VFor />-->


<!-- <VSlot>Editar usuário!</VSlot>-->
<!-- <Card>-->
<!-- <template v-slot:header>-->
<!-- <h1>Título do meu card</h1>-->
<!--</template>-->

<!--<template #content>-->
<!-- <h1>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab, saepe!</h1>-->
<!--</template>-->
<!--  </Card>-->

<!--</template>-->

<!--  <VPre />-->

<!--<VOnce />-->
<!--<VMemo />-->

<Options />
</template>
