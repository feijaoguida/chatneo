<template>
  <div class="button d-flex flex-column align-items-center">
    <b-button @click="$emit('click')" variant="danger" class="button pt-2">
      <b-icon font-scale="3" :icon="icon"></b-icon>
    </b-button>
    <div>
      <p class="font">{{label}}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    icon: { type: String, required: false },
    label: { type: String, required: true }
  }
};
</script>

<style scoped>
.button {
  max-width: 80px;
  max-height: 80px;
}

.font {
  font-size: 0.9rem;
  color: #343a40;
}
</style>
