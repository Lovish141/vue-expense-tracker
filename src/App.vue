<template>
  <HeaderComponent/>
  <div class="container">
    <BalanceComponent/>
    <IncomeExpenses/>
    <TransactionList/>
    <AddTransaction/>
  </div>
</template>

<script setup>
import BalanceComponent from './components/BalanceComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import IncomeExpenses from './components/IncomeExpenses.vue';
import TransactionList from './components/TransactionList.vue';
import AddTransaction from './components/AddTransaction.vue';
</script>

<style>

</style>