<script setup>
    import { ref, defineEmits } from 'vue'

    const exercises = ref([
        { id: 1, name: 'Running', duration: 30, calories: 300 },
        { id: 2, name: 'Cycling', duration: 45, calories: 400 }
    ])

    const emit = defineEmits(['exercise-selected'])

    const selectExercise = (exercise) => {
        emit('exercise-selected', exercise)
    }

</script>

<template>
    <h3>Exercise List</h3>
    <ul class="list">
        <li v-for="exercise in exercises" :key="exercise.id" @click="selectExercise(exercise)">
            {{ exercise.name }}
        </li>
    </ul>
</template>