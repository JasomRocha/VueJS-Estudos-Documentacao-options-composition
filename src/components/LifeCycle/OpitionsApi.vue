<template>
  <h1>Options Api</h1>
  <p>Contador: {{ counter }} </p>
  <button @click="counter++">Somar</button>
</template>

<script>
export default {
  name: "OpitionsApi",
  data(){
    return {
      counter: 0
    }
  },
  beforeCreate(){
    console.log("1 - before Create");
  },
  created(){
    console.log("2 - Created");
  },
  beforeMount(){
    console.log("3 - before Mount");
  },
  mounted(){
    console.log("4 - Mounted");
  },
  beforeUpdate(){
    console.log("5 - before Update");
  },
  updated(){
    console.log("6 - Updated");
  },
  beforeDestroy(){
    console.log("7 - before destroy");
  },
  destroyed(){
    console.log("8 - Destroyed");
  }
}
</script>
<style scoped>

</style>
