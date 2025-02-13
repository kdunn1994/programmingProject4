<script>
import { ref, defineEmits } from 'vue'

const name = ref('')
const duration = ref('')

const emit = defineEmits(['exerciseSubmitted'])

const onSubmit = () => {
    const exerciseData = {
        name: name.value,
        duration: parseFloat(duration.value),
        calories: parseFloat(duration.value) * 10
    }

    emit('exerciseSubmitted', exerciseData)

    name.value = ''
    duration.value = ''
}
</script>

<template>
    <h3>Add a new Exercise</h3>
    <form @submit.prevent="onSubmit">
        <div class="form-control">
            <label for="name">Exercise Name</label>
             <input type="text" id="name" v-model="name" placeholder="Enter Exercise Name...">            
        </div>
        <div class="form-control">
            <label for="duration">Duration (minutes)</label>
            <input type="text" id="duration" v-model="duration" placeholder="Enter Duration...">
        </div>
        <button class="btn">Add Exercise</button>
    </form>
</template>