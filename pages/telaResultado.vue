<template>
  <b-row class="d-flex flex-row container w-100">
    <b-col cols="4" class="d-flex flex-column container align-items-center">
      <div class="d-flex w-100 flex-column container align-items-center">
        <p>Como podemos te ajudar</p>
        <b-input-group class="mb-2">
          <b-form-input aria-label="Large text input with switch"></b-form-input>
          <b-input-group-append is-text>
            <b-icon icon="search"></b-icon>
          </b-input-group-append>
        </b-input-group>
        <p>ASSUNTOS MAIS BUSCADOS</p>
      </div>
      <div class="d-flex flex-column w-100 justify-content-between">
        <ButtonSide
          v-for="(btn, idx) in buttons"
          :key="idx"
          :pressed="btn.state"
          :label="btn.label"
          @click="openChild(btn)"
        />
      </div>
    </b-col>
    <b-col class="d-flex flex-column container align-items-center">
      <NuxtChild />
    </b-col>
  </b-row>
</template>

<script>
export default {
  data() {
    return {
      buttons: [
        { label: "Cadastro", child: "cadastroChild", state: false },
        { label: "Entregas", child: "entregasChild", state: false },
        { label: "Trocas", child: "trocasChild", state: false },
        { label: "Pedidos", child: "pedidosChild", state: false },
        { label: "Produtos", child: "produtosChild", state: false },
        { label: "Cadastre-se", child: "formChild", state: false }
      ]
    };
  },
  methods: {
    openChild(btn) {
      this.$router.push(`/telaResultado/${btn.child}`);
      this.buttons.map(b => (b.state = false));
      btn.state = true;
    }
  }
};
</script>


