<script setup>
    import { defineProps, defineEmits } from 'vue'

    const props = defineProps({
        exercises: {
            type: Array,
            required: true
        }
    })

    const emit = defineEmits(['exercise-selected', 'exercise-deleted'])

    const selectExercise = (exercise) => {
        emit('exercise-selected', exercise)
    }

    const deleteExercise = (id) => {
        emit('exercise-deleted', id)
    }

</script>

<template>
    <h2>Exercise List</h2>
    <ul class="list">
        <li v-for="exercise in exercises" :key="exercise.id" @click="selectExercise(exercise)">
            {{ exercise.name }}
            <button @click.stop="deleteExercise(exercise.id)" class="delete-btn">X</button>
        </li>
    </ul>
</template>