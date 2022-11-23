<template>
  <section class="columns m-4 is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <h2 class="is-size-3">Make a question!</h2>
    <div class="control column">
      <input class="input" v-model="newQuestion" type="text" placeholder="Question...">
    </div>
    <button class="button">Submit</button>
    <p>{{ capitalize() }}</p>
  </section>
</template>
<script setup lang="ts">
import { ref } from 'vue';

// interface Props {
//   items: {
//     q_id: number;
//     question: string;
//   };
// }
// const props = defineProps<Props>()

const newQuestion = ref("")

function capitalize() {
  return newQuestion.value.charAt(0).toUpperCase() + newQuestion.value.slice(1)
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