<template>
  <div class="d-flex w-100 flex-column container">
    <div>
      <h4>Cadastro</h4>
    </div>
    <div class="w-100">
      <span
        class="align-items-lg-start w-100 fontSize"
        v-b-toggle.collapse-1
        @click="visible = !visible"
      >
        <b-icon class="mr-2" font-scale="1" :icon="visible ? 'chevron-down' : 'chevron-right'"></b-icon>Como me cadastrar no site?
      </span>
      <b-collapse class="mt-2 ml-4" id="collapse-1">
        <p class="fontSize">
          Collapse contents Here Lorem ipsum dolor sit amet
          consectetur adipisicing elit. Id possimus, illum similique
          accusantium, nisi in nemo, nesciunt quos ea quae autem debitis
          perferendis est vitae odit aperiam velit eveniet repellendus.
        </p>
        <div>
          <span class="fontSize">Essa resposta Foi util</span>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="resposta = 'SIM'"
            variant="success"
          >Sim</b-button>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="resposta = 'NAO'"
            variant="danger"
          >Não</b-button>
        </div>
        <div class="mt-3" v-if="resposta == 'SIM'">
          <p class="title fontSize">Que bom que conseguimos ajudar</p>
          <p
            class="text-muted fontSize"
          >Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
        <div class="mt-3" v-if="resposta == 'NAO'">
          <p class="title fontSize">Sentimos por não ajudar</p>
          <p
            class="text-muted fontSize"
          >Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
      </b-collapse>
    </div>
    <div class="w-100">
      <span
        class="align-items-lg-start w-100 fontSize"
        v-b-toggle.collapse-2
        @click="visible2 = !visible2"
      >
        <b-icon class="mr-2" font-scale="1" :icon="visible2 ? 'chevron-down' : 'chevron-right'"></b-icon>Como recupero minha Senha?
      </span>
      <b-collapse class="mt-2 ml-4" id="collapse-2">
        <p class="fontSize">
          Collapse contents Here Lorem ipsum dolor sit amet
          consectetur adipisicing elit. Id possimus, illum similique
          accusantium, nisi in nemo, nesciunt quos ea quae autem debitis
          perferendis est vitae odit aperiam velit eveniet repellendus.
        </p>
        <div>
          <span class="fontSize">Essa resposta Foi util</span>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="resposta = 'SIM'"
            variant="success"
          >Sim</b-button>
          <b-button
            class="fontSize"
            size="sm"
            squared
            @click="resposta = 'NAO'"
            variant="danger"
          >Não</b-button>
        </div>
        <div class="mt-3" v-if="resposta == 'SIM'">
          <p class="title fontSize">Que bom que conseguimos ajudar</p>
          <p
            class="text-muted fontSize"
          >Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
        <div class="mt-3" v-if="resposta == 'NAO'">
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
      visible: false,
      visible2: false,
      resposta: ""
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
