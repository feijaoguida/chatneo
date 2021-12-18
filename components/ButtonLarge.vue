<template>
  <b-button @click="$emit('click')" variant="danger" class="pt-2">
    <b-icon :font-scale="scale" :icon="icon"></b-icon>
    <div>{{description}}</div>
  </b-button>
</template>

<script>
export default {
  props: {
    icon: { type: String, required: false },
    description: { type: String, required: true },
    scale: { type: String, required: false }
  }
};
</script>
