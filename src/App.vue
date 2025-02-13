<script setup>
import ExerciseDetails from './components/ExerciseDetails.vue';
import ExerciseList from './components/ExerciseList.vue';
import Header from './components/Header.vue';
import ExerciseSummary from './components/ExerciseSummary.vue';
import AddExercise from './components/AddExercise.vue'

import { ref, computed } from 'vue'

const selectedExercise = ref(null)
const exercises = ref([])

const handleExerciseSelected = (exercise) => {
  selectedExercise.value = exercise
}

const handleExerciseSubmitted = (exerciseData) => {
  exercises.value.push({
    id: generateID(),
    name: exerciseData.name,
    duration: exerciseData.duration,
    calories: exerciseData.calories,
  })
}

const generateID = () => {
  return Math.floor(Math.random() * 10000000)
}

const totalCalories = computed(() => {
  return exercises.value.reduce((sum, exercise) => sum + exercise.calories, 0)
})

</script>



<template>
  <Header></Header>
  <div class="container">
    <ExerciseList :exercises="exercises" @exercise-selected="handleExerciseSelected"></ExerciseList>
    <ExerciseDetails :selectedExercise="selectedExercise"></ExerciseDetails>
    <ExerciseSummary :totalCalories="totalCalories"></ExerciseSummary>
    <AddExercise @exerciseSubmitted="handleExerciseSubmitted"></AddExercise>
  </div>


</template>