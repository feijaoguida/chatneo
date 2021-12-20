<template>
  <b-row class="d-flex flex-wrap flex-row w-100 flexAjuste">
    <b-col cols="5" class="d-flex flex-column align-items-center maxWidth">
      <div class="d-flex w-100 flex-column align-items-center">
        <p>Como podemos te ajudar</p>
        <b-input-group size="sm" class="mb-4">
          <b-form-input type="search" placeholder="Ex.: Como posso acompanha meu pedido?"></b-form-input>
          <b-input-group-append is-text>
            <b-icon font-scale="1" icon="search"></b-icon>
          </b-input-group-append>
        </b-input-group>
        <p>ASSUNTOS MAIS BUSCADOS</p>
      </div>
      <div class="d-flex flex-column w-100 justify-content-between maxHeight">
        <ButtonSide
          v-for="(btn, idx) in buttons"
          :key="idx"
          :pressed="btn.state"
          :label="btn.label"
          @click="openChild(btn)"
        />
      </div>
    </b-col>
    <b-col class="d-flex flex-column align-items-center w-100">
      <NuxtChild />
      <IconChat />
      <div class="flutuante">
        <Rodape
          class="w-50 float-left"
          style="position: relative;
                  min-height: 50vh !important;"
        />
      </div>
    </b-col>
  </b-row>
</template>

<script>
export default {
  layout: "layoutsPages",
  data() {
    return {
      buttons: [
        { label: "Cadastro", child: "cadastroChild", state: false },
        { label: "Entregas", child: "entregasChild", state: false },
        { label: "Trocas", child: "trocasChild", state: false },
        { label: "Pedidos", child: "pedidosChild", state: false },
        { label: "Produtos", child: "produtosChild", state: false }
      ]
    };
  },
  methods: {
    openChild(btn) {
      this.$router.push(`/telaResultado/${btn.child}`);
      this.buttons.map(b => (b.state = false));
      btn.state = true;
    },
    setarButton() {
      let path = this.$route.path.split("/");
      this.buttons.map(b => {
        if (b.child == path[2]) b.state = true;
      });
    }
  },
  mounted() {
    this.setarButton();
  }
};
</script>

<style scoped>
@media (max-width: 576px) {
  .flexAjuste {
    flex-direction: column !important;
  }

  .maxWidth {
    max-width: 100% !important;
  }

  .maxHeight {
    flex-wrap: wrap;
    height: 145px;
  }

  .mb-5 {
    margin-bottom: 1rem !important;
  }

  .flutuante {
    right: 1em;
    bottom: 0;
    margin-bottom: 2em;
    margin-top: 2em;
    z-index: 200;
  }
}
</style>




