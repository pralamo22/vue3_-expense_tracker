<template>
  <h3>Historial</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      v-bind:key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>{{ transaction.amount }} €</span>
      <button class="delete-btn">x</button>
    </li>

    <!-- <li
      v-for="transaction in transactions"
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>{{ transaction.amount }}€</span
      ><button class="delete-btn" @click="deleteTransaction(transaction.id)">
        x
      </button>
    </li> -->
  </ul>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

// const transactions = [
//   { id: 1, text: "Flower", amount: -19.99 },
//   { id: 1, text: "Salario", amount: 299.97 },
//   { id: 1, text: "Book", amount: -10 },
//   { id: 1, text: "Camara", amount: -150 },
// ];

// Comentado el aspecto del código para el Options API. Ahora, con
// setup, utilizamos el Composition API.
// export default {
//   data() {
//     return {
//       transactions: [
//         { id: 1, text: "Flower", amount: -19.99 },
//         { id: 1, text: "Salario", amount: 299.97 },
//         { id: 1, text: "Book", amount: -10 },
//         { id: 1, text: "Camara", amount: -150 },
//       ],
//     };
//   },
//   methods: {},
// };
</script>

<style lang="css" scoped></style>
