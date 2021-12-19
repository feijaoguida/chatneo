<template>
  <div>
    <p class="h6 align-self-center text-center text-muted">Sua compra foi feita hein:</p>
    <div class="m-5 w-button d-flex justify-content-around">
      <ButtonLarge @click="link" description="Loja Online" scale="3" icon="Phone" />
      <ButtonLarge @click="linkExterno" description="Loja Física" scale="3" icon="shop" />
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",

  methods: {
    linkExterno() {
      window.open("https://linktr.ee/rbgsolucoes", "_blank");
    },

    link() {
      this.$router.push(`/telaBusca`);
    }
  }
};
</script>

<style scoped>
.w-button {
  width: 300px !important;
}
</style>
