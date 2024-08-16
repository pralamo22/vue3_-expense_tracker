<template>
  <Header />
  <div class="container">
    <Balance :total="total" />
    <IncomeExpenses :income="+income" :expenses="+expenses" />
    <TransactionList :transactions="transactions" />
    <AddTransaction />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransactionList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed } from "vue";

const transactions = ref([
  { id: 1, text: "Flower", amount: -19.98 },
  { id: 1, text: "Salario", amount: 299.97 },
  { id: 1, text: "Book", amount: -10 },
  { id: 1, text: "Camara", amount: -150 },
]);

console.log(transactions);
console.log(transactions.value);

//Calculamos el total
const total = computed(() => {
  return transactions.value.reduce((acc, transaction) => {
    return acc + transaction.amount;
  }, 0);
});

//Calculamos las entradas
const income = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount > 0)
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});

//Calculamos las salidas
const expenses = computed(() => {
  return transactions.value
    .filter((transaction) => transaction.amount < 0)
    .reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
    .toFixed(2);
});
</script>

<script>
// Comentado el aspecto del código para el Options API. Ahora, con
// setup, utilizamos el Composition API.
// export default {
//   components: {
//     Header,
//     Balance,
//     IncomeExpenses,
//     TransactionList,
//     AddTransaction
//   },
// };
</script>
<!-- hola -->
<style lang="css" scoped></style>
