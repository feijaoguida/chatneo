<template>
  <b-container class="mt-5 d-flex flex-column align-items-center">
    <p class="h4">CENTRAL DE ATENDIMENTO</p>
    <p class="h6">
      <b-icon icon="tools"></b-icon>Sua compra foi feita hein
    </p>
    <div class="w-50 d-flex justify-content-around">
      <b-button variant="danger" class="pt-4 pb-4">
        <b-icon icon="Phone"></b-icon>
        <p>Loja Online</p>
      </b-button>
      <b-button variant="danger" class="pt-4 pb-4">
        <b-icon icon="shop"></b-icon>
        <p>Loja Fisica</p>
      </b-button>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "IndexPage"
};
</script>
