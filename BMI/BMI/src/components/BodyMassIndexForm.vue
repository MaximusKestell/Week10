<script setup>
import { ref } from 'vue'

// defineProps({
//   // extra question needs this, basic app does not
// })

// define the messages this component may send to other components
const emit = defineEmits([
  'stats-entered' // we can pick these names - this message will
  // be sent once the user has entered their data and the app should do math
])

const height = ref('0')
const weight = ref('0')
// todo weight

function statsEntered() {
  // todo send this data - height and weight to App.vue to do the math
  // make sure to include weight

  if (height.value <= 0 || height > 3 || height.value === '' || isNaN(height.value)) {
    alert('enter valid height')
  }
  emit('stats-entered', height.value) // goes to components parent
  // where does the message go? App.vue
}

// const count = ref(0)




</script>

<template>

  <h2>BMI Form</h2>

  <label>Height in meters </label>
  <input type="number" v-model="height">

<!--  todo weight input-->

  <button v-on:click="statsEntered">Calculate</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
