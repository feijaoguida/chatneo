<template>
  <div class="d-flex w-100 flex-column container">
    <div>
      <h4>Cadastro</h4>
    </div>
    <div class="w-100" v-for="(item, idx) in items" :key="idx">
      <span
        class="align-items-lg-start w-100 fontSize"
        v-b-toggle="`${item.toggle}`"
        @click="item.visible = !item.visible"
      >
        <b-icon class="mr-2" font-scale="1" :icon="item.visible ? 'chevron-down' : 'chevron-right'"></b-icon>
        {{item.pergunta}}
      </span>
      <b-collapse class="mt-2 ml-4" :id="item.toggle">
        <p class="fontSize">{{item.texto}}</p>
        <div>
          <span class="fontSize">Essa resposta Foi util</span>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="item.resposta = 'SIM'"
            variant="success"
          >Sim</b-button>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="item.resposta = 'NAO'"
            variant="danger"
          >Não</b-button>
        </div>
        <div class="mt-3" v-if="item.resposta == 'SIM'">
          <p class="title fontSize">Que bom que conseguimos ajudar</p>
          <p
            class="text-muted fontSize"
          >Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
        <div class="mt-3" v-if="item.resposta == 'NAO'">
          <p class="title fontSize">Sentimos por não ajudar</p>
          <p
            class="text-muted fontSize"
          >Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
      </b-collapse>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          visible: false,
          resposta: "",
          toggle: "toggle1",
          pergunta: "Como me cadastrar no site?",
          texto:
            "Collapse contents Here Lorem ipsum dolor sit amet consectetur adipisicing elit. Id possimus, illum similique accusantium, nisi in nemo, nesciunt quos ea quae autem debitis perferendis est vitae odit aperiam velit eveniet repellendus."
        },
        {
          visible: false,
          resposta: "",
          toggle: "toggle2",
          pergunta: "Como recupero minha senha?",
          texto:
            "Collapse contents Here Lorem ipsum dolor sit amet consectetur adipisicing elit. Id possimus, illum similique accusantium, nisi in nemo, nesciunt quos ea quae autem debitis perferendis est vitae odit aperiam velit eveniet repellendus."
        },
        {
          visible: false,
          resposta: "",
          toggle: "toggle3",
          pergunta: "é possível comprar no site sem me cadastrar?",
          texto:
            "Collapse contents Here Lorem ipsum dolor sit amet consectetur adipisicing elit. Id possimus, illum similique accusantium, nisi in nemo, nesciunt quos ea quae autem debitis perferendis est vitae odit aperiam velit eveniet repellendus."
        }
      ]
    };
  }
};
</script>

<style scoped>
@media (max-width: 720px) {
  .fontSize {
    font-size: 0.8em;
  }
}

.textSpan {
  text-align: left;
}
</style>
