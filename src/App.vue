<script setup>
import ExerciseDetails from './components/ExerciseDetails.vue';
import ExerciseList from './components/ExerciseList.vue';
import Header from './components/Header.vue';

</script>



<template>
  <header></header>
  <div class="container">
    <ExerciseList @exercise-selected="handleExerciseSelected"></ExerciseList>
    <ExerciseDetails :selectedExercise="selectedExercise"></ExerciseDetails>
  </div>


</template>