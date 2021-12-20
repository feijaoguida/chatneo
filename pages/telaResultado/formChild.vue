<template>
  <div class="d-flex w-100 flex-column container">
    <div>
      <h5>ATENDIMENTO VIA E-MAIL</h5>
      <p>Preencha dos campos abaixo e nos envie um e-mail:</p>
    </div>
    <div v-if="!enviar" class="w-100">
      <b-form>
        <b-form-group id="input-group-3" label="Assunto:" label-for="input-3">
          <b-form-select
            id="input-3"
            :state="false"
            v-model="form.assunto"
            :options="assuntos"
            required
          ></b-form-select>
          <b-form-invalid-feedback :state="false">O Campo assunto é obrigatório!</b-form-invalid-feedback>
        </b-form-group>
        <b-form-group id="input-group-2" label="Nome:" label-for="input-2">
          <b-form-input id="input-2" v-model="form.name" placeholder="Insira seu nome" required></b-form-input>
          <b-form-invalid-feedback :state="false">O Campo nome é obrigatório!</b-form-invalid-feedback>
        </b-form-group>
        <b-form-group id="input-group-1" label="Email:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            placeholder="Insira seu e-mail"
            required
          ></b-form-input>
          <b-form-invalid-feedback :state="false">O Campo e-mail é obrigatório!</b-form-invalid-feedback>
        </b-form-group>
        <b-form-group id="input-group-1" label="Anexos" label-for="input-1">
          <b-form-file
            v-model="form.file"
            :state="Boolean(form.file)"
            placeholder="Nenhum arquivo selecionado"
          ></b-form-file>
          <div class="mt-3">Arquivos selecionados: {{ form.file ? form.file.name : '' }}</div>
        </b-form-group>
        <b-form-group id="input-group-1" label="Mensagem" label-for="input-1">
          <b-form-textarea
            id="textarea"
            v-model="form.text"
            placeholder="Sobre o que deseja falar?"
            rows="3"
            max-rows="6"
          ></b-form-textarea>
        </b-form-group>
        <b-button
          @click="enviar = true"
          type="submit"
          class="float-right"
          variant="success"
        >ENVIAR FORMULÁRIO</b-button>
      </b-form>
    </div>
    <div v-else class="d-flex justify-content-center flex-column align-items-center">
      <b-card bg-variant="success" text-variant="white" class="m-2 p-0 fontSize w-75 text-left">
        <b-card-text>
          Seu e-mail foi enviado com sucesso! Seu número de protocolo é
          <strong>XXXXXX</strong>. Aguarde, em breve entraremos em contato!
        </b-card-text>
      </b-card>
      <b-button @click="enviar = false" variant="light" class="w-50 pt-2 bg-transparent">
        <b-icon variant="danger" icon="chevron-left"></b-icon>
        <span class="text-info">RETORNAR À TELA INICIAL</span>
      </b-button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enviar: false,
      visible: false,
      resposta: "",
      form: {
        email: "",
        name: "",
        assunto: null,
        checked: [],
        file: null,
        text: ""
      },
      assuntos: [
        { text: "Select One", value: null },
        "Cadastro",
        "Entrega",
        "Troca",
        "Pedido",
        "Produto"
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
