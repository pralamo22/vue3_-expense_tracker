<template>
  <Header />
  <div class="container">
    <Balance />
    <IncomeExpenses />
    <TransactionList />
    <AddTransaction />

  </div>
</template>

<script setup>
  import Header from './components/Header.vue';
  import Balance from './components/Balance.vue';
  import IncomeExpenses from './components/IncomeExpenses.vue';
  import TransactionList from './components/TransactionList.vue';
  import AddTransaction from './components/AddTransaction.vue';
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
<style lang="css" scoped>

</style>