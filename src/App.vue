<template>
  <CompositionCard
    title="Esse é o meu título"
    :body="'Esse é o meu card'"
    :access=123
    :status=true
    format="company" />
</template>

<script>
import {defineComponent} from "vue";
import CompositionCard from "./components/Props/CompositionCard.vue";

export default defineComponent({
  components: {CompositionCard}
})

</script>
