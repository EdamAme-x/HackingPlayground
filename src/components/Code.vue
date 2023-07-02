<template>
  <font v-bind:color="props.color">{{ text }}</font>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
    },
    text: {
      type: String,
    },
  },
};
</script>

<style scoped></style>
