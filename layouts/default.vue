<template>
  <b-container fluid="xl" class="mt-5 d-flex flex-column align-items-center">
    <p class="h4 m-5">CENTRAL DE ATENDIMENTO</p>

    <Nuxt />

    <div class="innerdiv">
      <Assist />
    </div>
  </b-container>
</template>

<style scoped>
.innerdiv {
  position: absolute;
  float: right;
  right: 1em;
  bottom: 0;
  margin-bottom: 2em;
  /* Push it up into the element before it. This is a trick for bottom-right */
  right: 1em;
  z-index: 200;
}
</style>
