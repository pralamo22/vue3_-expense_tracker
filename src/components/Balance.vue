<template>
  <h4>Saldo</h4>
  <h1 id="balance">{{ total.toFixed(2) }}€</h1>
  <div></div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>

<style lang="css" scoped></style>
