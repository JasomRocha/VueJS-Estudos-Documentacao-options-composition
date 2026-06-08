<template>
  <button>
<!--no slot colocamos um valor padrão, um fallback -->
<!-- caso o componente pai não passe nada pra ele então ele insere um valor padrão que nesse caso é 'Salvar'-->
    <slot>Salvar</slot>
  </button>
</template>

