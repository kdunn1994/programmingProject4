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
        <h2>Exercise Summary</h2>
        <p>Total Calories Burned: {{ totalCalories }}</p>
    </div>
</template>