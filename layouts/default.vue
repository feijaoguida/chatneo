<template>
  <b-container fluid="md" class="mt-5 maxWidth d-flex flex-column align-items-center mw">
    <p class="h6 m-5 text-center">CENTRAL DE ATENDIMENTO</p>

    <Nuxt />

    <div class="w-100 d-flex flex-column align-items-end innerdiv mt-5">
      <Assist />
    </div>
  </b-container>
</template>

<style scoped>
.innerdiv {
  position: relative;
  float: right;
  right: 1em;
  bottom: 0;
  margin-bottom: 2em;
  margin-top: 2em;
  z-index: 200;
}

.maxWidth {
  max-width: 720px !important;
}
</style>
