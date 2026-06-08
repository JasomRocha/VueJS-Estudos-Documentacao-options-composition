<template>
  <div>
    <header style="color: red">
      <slot name="header"></slot>
    </header>
  </div>

  <div style="background: yellow">
    <slot name="image"></slot>
  </div>

  <main style="color: green">
    <slot name="content"></slot>
  </main>

</template>

<script setup>

</script>
