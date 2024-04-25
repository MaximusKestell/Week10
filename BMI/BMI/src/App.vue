<!--http://localhost:5173/-->
<script setup>

import { ref } from 'vue'
import BodyMassIndexForm from './components/BodyMassIndexForm.vue'

const bmi = ref(0)

const calculateBMI = (height) => {
  alert('todo - do math. height is ' + height)
  bmi.value = height // todo actualy do math
}

</script>

<template>
<!--HTML for component-->
  <div>
  <h1>Body Mass Index Calculator</h1>
  </div>

  <BodyMassIndexForm/>
  <h2>BMI is: {{ bodyMassIndex }}</h2>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
