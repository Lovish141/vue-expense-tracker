<template>
  <HeaderComponent/>
  <div class="container">
    <BalanceComponent :total="total"/>
    <IncomeExpenses :income="income" :expense="expense"/>
    <TransactionList :transactions="transactions"/>
    <AddTransaction/>
  </div>
</template>

<script setup>
import BalanceComponent from './components/BalanceComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import IncomeExpenses from './components/IncomeExpenses.vue';
import TransactionList from './components/TransactionList.vue';
import AddTransaction from './components/AddTransaction.vue';

import {computed, ref} from 'vue'

const transactions=ref([
  {id:1,text:"Flower",amount:-19.99},
  {id:2,text:"Salary",amount:300}
])

const total=computed(()=>{
  return (transactions.value.reduce((acc, transaction) =>
     acc + transaction.amount
  , 0))});



const income = computed(() => {
  return parseFloat(transactions.value
    .filter((transaction) => transaction.amount > 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0)
    .toFixed(2));
});

// Get expenses
const expense = computed(() => {
  return parseFloat(transactions.value
    .filter((transaction) => transaction.amount < 0)
    .reduce((acc, transaction) => acc + transaction.amount, 0)
    .toFixed(2));
});
console.log(income)

</script>

<style>

</style>