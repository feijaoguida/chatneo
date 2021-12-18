<template>
  <div class="d-flex w-100 flex-column container">
    <div>
      <h3>Cadastro</h3>
    </div>
    <div class="w-100">
      <span class="align-items-lg-start w-100" v-b-toggle.collapse-1 @click="visible = !visible">
        <b-icon class="mr-2" font-scale="1" :icon="visible ? 'chevron-down' : 'chevron-right'"></b-icon>Como me cadastrar no site?
      </span>
      <b-collapse id="collapse-1" class="mt-2 ml-4">
        <p>
          Collapse contents Here Lorem ipsum dolor sit amet
          consectetur adipisicing elit. Id possimus, illum similique
          accusantium, nisi in nemo, nesciunt quos ea quae autem debitis
          perferendis est vitae odit aperiam velit eveniet repellendus.
        </p>
        <div>
          <span>Essa resposta Foi util</span>
          <b-button size="sm" squared @click="resposta = 'SIM'">Sim</b-button>
          <b-button size="sm" squared @click="resposta = 'NAO'" variant="danger">Não</b-button>
        </div>
        <div class="mt-3" v-if="resposta == 'SIM'">
          <p class="title">Que bom que conseguimos ajudar</p>
          <p class="text-muted">Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
        </div>
        <div class="mt-3" v-if="resposta == 'NAO'">
          <p class="title">Sentimos por não ajudar</p>
          <p class="text-muted">Você mereçe o melhor atendimento e ficamos felizes em te ajudar</p>
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
      resposta: ""
    };
  }
};
</script>

<style scoped>
.textSpan {
  text-align: left;
}
</style>
