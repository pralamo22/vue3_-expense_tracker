<template>
  <h3>Nuevo movimiento</h3>
  <form id="form" @submit.prevent="onSubmit">
    <div class="form-control">
      <label for="text">Texto</label>
      <input type="text" id="text" v-model="text" placeholder="Enter text..." />
    </div>
    <div class="form-control">
      <label for="amount"
        >Cantidad <br />
        (negativa -> Salida, positiva -> Entrada)</label
      >
      <input
        type="text"
        id="amount"
        placeholder="Enter amount..."
        v-model="amount"
      />
    </div>
    <button class="btn">Add transaction</button>
  </form>
</template>

<script setup>
import { ref } from "vue";

const text = ref("");
const amount = ref("");

const onSubmit = () => {
  console.log(text.value, amount.value);
};
</script>

<style lang="css" scoped></style>
