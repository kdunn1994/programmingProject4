<script setup>
import { ref, computed, defineProps } from 'vue'

const props = defineProps({
    selectedExercise: {
        type: Object,
        requires: true
    }
})

const totalCalories = computed(() => {
    return props.selectedExercise.duration * 10;
})
</script>

<template>
    <div v-if="selectedExercise">
        <h1>{{ selectedExercise.name }}</h1>
        <ul>
            <li>Duration: {{ selectedExercise.duration }} minutes</li>
            <li>Calories: {{ totalCalories }}</li>
        </ul>
    </div>
</template>