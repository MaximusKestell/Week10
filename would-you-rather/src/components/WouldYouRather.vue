<script setup>
import { ref, watch } from 'vue'

defineProps({
  question: String,
  answer1: String,
  answer2: String
})

const emit = defineEmits([
    'answer-selected'
])

const choice = ref('')

// function choiceMade() {
//   // emit event to tell parent user has made choice
//   emit('answer-selected', choice.value)
// }

watch(choice, () => {
  emit('answer-selected', choice.value)
}) // this watches choice variable, when it changes, it emits value to parent

</script>

<template>
  <div id="wyr">

    <h2>Make your choice!</h2>

    <p>{{ question }}</p>
      <div>
        <input v-model="choice" v-bind:value="answer1"  type="radio" id="answer-1"> <!-- *v-model="choice" v-bind:value="answer1"* is what makes the radio buttons work properly and not allow one to select both buttons.-->
        <label for="answer-1">{{ answer1 }}</label>

        <input v-model="choice" v-bind:value="answer2"  type="radio" id="answer-2">
        <label for="answer-2">{{ answer2 }}</label>
      </div>
  </div>
</template>

<style scoped>

#wyr {
  background-color: hotpink;
}

p {
  font-family: fantasy;
}

</style>
