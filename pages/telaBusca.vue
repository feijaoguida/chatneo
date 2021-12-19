<template>
  <div class="d-flex flex-column container align-items-center">
    <div class="d-flex w-75 flex-column container align-items-center">
      <p class="h6 align-self-center mb-4 text-center text-muted">Como podemos te ajudar</p>
      <b-input-group size="sm" class="mb-5">
        <b-form-input type="search" placeholder="Ex.: Como posso acompanha meu pedido?"></b-form-input>
        <b-input-group-append is-text>
          <b-icon font-scale="1" icon="search"></b-icon>
        </b-input-group-append>
      </b-input-group>
      <p
        class="h6 mb-4 align-self-center text-center text-muted"
      >Navegue pelos assuntos mais buscados:</p>
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
