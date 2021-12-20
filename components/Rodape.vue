<template>
  <div class="w-100 d-flex flex-row align-items-center">
    <div class="w-35">
      <p
        class="fontSize"
      >Caso queira, você também pode nos enviar um e-mail ou falar com um de nossos atendentes via chat.</p>
    </div>
    <div class="d-flex flex-row">
      <b-icon @click="openChild" class="ml-3 mr-3 cursorPointer" scale="2" icon="envelope"></b-icon>
      <b-icon @click="$emit('click')" class="ml-3 cursorPointer" scale="2" icon="chat-text"></b-icon>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    openChild() {
      this.$router.push(`/telaResultado/formChild`);
    }
  }
};
</script>

<style scoped>
.fontSize {
  font-size: 0.7rem;
}

.cursorPointer {
  cursor: pointer;
}

.w-35 {
  width: 35%;
}
</style>
