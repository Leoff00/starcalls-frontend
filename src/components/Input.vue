<template>
  <section class="columns m-4 is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <h2 class="is-size-3">Make a question!</h2>
    <div class="control column">
      <input class="input" v-model="newQuestion" type="text" placeholder="Question...">
    </div>
    <button class="button" @click="createQuestion">Submit</button>
  </section>
</template>
<script setup lang="ts">
import { ref } from 'vue';

const emit = defineEmits(['new-q'])
const newQuestion = ref("")

function createQuestion() {
  emit('new-q', newQuestion.value)
}

</script>
<style scoped>
h2 {
  font-weight: 600;
  color: var(--soft-black-weak);
}

input::placeholder {
  color: var(--dark-black-strong);
}
</style>