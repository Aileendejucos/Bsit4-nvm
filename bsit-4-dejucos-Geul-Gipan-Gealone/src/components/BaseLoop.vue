<script setup>
import { ref } from 'vue'
let numbers = ref([0, 1, 2, 3, 4, 5, "string"])

</script>
<template>
    <ul>
        <li v-for="number in numbers">
            {{ number }}
        </li>
    </ul>
    <button @click="numbers.push('Done')">Click</button>
</template>