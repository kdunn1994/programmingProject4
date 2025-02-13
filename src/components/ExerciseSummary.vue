<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    totalCalories: {
        type: Number,
        required: true
    }
})
</script>

<template>
    <div>
        <h1>Exercise Summary</h1>
        <p>Total Calories Burned: {{ totalCalories }}</p>
    </div>
</template>