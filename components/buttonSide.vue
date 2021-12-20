<template>
  <b-button
    class="button d-flex justify-content-between m-1 align-items-center"
    @click="$emit('click')"
    variant="danger"
    :pressed="pressed"
  >
    <span>{{label}}</span>
    <b-icon icon="chevron-right"></b-icon>
  </b-button>
</template>

<script>
export default {
  props: {
    label: { type: String, required: true },
    pressed: { type: Boolean }
  }
};
</script>

<style scoped>
.button {
  max-width: -webkit-fill-available;
  min-width: fit-content;
}
</style>
