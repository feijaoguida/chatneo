<template>
  <b-img class="pointer" @click="goHome" src="~/static/neoassist.png"></b-img>
</template>

<script>
export default {
  methods: {
    goHome() {
      this.$router.push(`/`);
    }
  }
};
</script>

<style scoped>
.pointer {
  cursor: pointer;
}
</style>
