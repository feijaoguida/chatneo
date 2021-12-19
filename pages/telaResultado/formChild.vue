<template>
  <div class="d-flex w-100 flex-column container">
    <div>
      <h3>ATENDIMENTO VIA E-MAIL</h3>
      <h5>Preencha dos campos abaixo e nos envie um e-mail:</h5>
    </div>
    <div class="w-100">
      <b-form>
        <b-form-group id="input-group-3" label="Assunto:" label-for="input-3">
          <b-form-select
            id="input-3"
            :state="false"
            v-model="form.assunto"
            :options="assuntos"
            required
          ></b-form-select>
          <b-form-invalid-feedback :state="false">Your user ID must be 5-12 characters long.</b-form-invalid-feedback>
        </b-form-group>
        <b-form-group id="input-group-2" label="Nome:" label-for="input-2">
          <b-form-input id="input-2" v-model="form.name" placeholder="Insira seu nome" required></b-form-input>
        </b-form-group>
        <b-form-group id="input-group-1" label="Email:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            placeholder="Insira seu e-mail"
            required
          ></b-form-input>
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
        <b-button type="submit" variant="primary">ENVIAR FORMULÁRIO</b-button>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
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
.textSpan {
  text-align: left;
}
</style>
