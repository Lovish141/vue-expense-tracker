<template>
  <div class="inc-exp-container">
    <div>
        <h4>Income</h4>
        <p class="money plus" id="money-plus">
           + ${{ props.income}}
        </p>
    </div>
    <div>
        <h4>Expense</h4>
        <p class="money minus" id="money-minus">
            -${{ props.expense }}
        </p>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';
const props=defineProps({
  income:{
    type:Number,
    required:true,
  },
  expense:{
    type:Number,
    required:true
  }
})
</script>