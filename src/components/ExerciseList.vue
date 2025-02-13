<script setup>
    import { defineProps, defineEmits } from 'vue'

    const props = defineProps({
        exercises: {
            type: Array,
            required: true
        }
    })

    const emit = defineEmits(['exercise-selected'])

    const selectExercise = (exercise) => {
        emit('exercise-selected', exercise)
    }

</script>

<template>
    <h2>Exercise List</h2>
    <ul class="list">
        <li v-for="exercise in exercises" :key="exercise.id" @click="selectExercise(exercise)">
            {{ exercise.name }}
        </li>
    </ul>
</template>