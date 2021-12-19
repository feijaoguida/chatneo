<template>
  <b-container fluid="xl" class="mt-5 d-flex flex-column align-items-center">
    <p class="h4 m-5">CENTRAL DE ATENDIMENTO</p>

    <Nuxt />

    <div class="w-100 d-flex flex-column align-items-end innerdiv">
      <div style="font-size: 2rem;">
        <b-icon icon="chat" class="rounded-circle bg-danger p-2" variant="light"></b-icon>
      </div>
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
  /* Push it up into the element before it. This is a trick for bottom-right */

  z-index: 200;
}
</style>
