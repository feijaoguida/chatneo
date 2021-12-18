<template>
  <div class="d-flex flex-column container align-items-center">
    <div class="d-flex w-75 flex-column container align-items-center">
      <p>Como podemos te ajudar</p>
      <b-input-group size="lg" class="mb-2">
        <b-form-input aria-label="Large text input with switch"></b-form-input>
        <b-input-group-append is-text>
          <b-icon icon="search"></b-icon>
        </b-input-group-append>
      </b-input-group>
      <p>Navegue pelos assuntos mais buscados</p>
    </div>
    <div class="d-flex flex-row w-100 justify-content-between">
      <ButtonLabelDown @click="navegarTela" label="Cadastro" icon="person-fill" />
      <ButtonLabelDown @click="navegarTela" label="Entregas" icon="truck" />
      <ButtonLabelDown @click="navegarTela" label="Trocas" icon="arrow-down-up" />
      <ButtonLabelDown @click="navegarTela" label="Pedidos" icon="bag" />
      <ButtonLabelDown @click="navegarTela" label="Produtos" icon="lamp-fill" />
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    navegarTela() {
      this.$router.push(`/telaResultado`);
    }
  }
};
</script>
