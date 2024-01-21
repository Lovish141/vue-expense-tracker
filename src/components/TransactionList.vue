<template>
    <h3>History</h3>
    <ul id="list" class="list">
        <li class="minus" v-for="transaction in props.transactions" :key="transaction.id">
           {{ transaction.text}} <span>${{ transaction.amount }}</span>
           <button class="delete-btn">X</button>
        </li>
    </ul>
</template>

<script setup>
import { defineProps } from 'vue';

const props=defineProps({
    transactions:{
        type:Array,
        required:true
    }
})
</script>