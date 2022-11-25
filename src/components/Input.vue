<template>
  <section class="columns m-4 is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <h2 class="is-size-3">Make a question!</h2>
    <div class="control column">
      <input class="input" v-model="newQuestion" type="text" placeholder="Question...">
    </div>
    <button class="button" @click="emit('submitted', capitalize)">Submit</button>
  </section>
</template>
<script setup lang="ts">
import { ref, computed } from 'vue';

const emit = defineEmits<{ (e: 'submitted', capitalize: string): void }>()
const newQuestion = ref("")

const capitalize = computed(() => newQuestion.value.charAt(0).toUpperCase() + newQuestion.value.slice(1))

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