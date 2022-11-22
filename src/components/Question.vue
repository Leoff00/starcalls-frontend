<template>
  <div class="qa-container column m-6">
    <div class="mt-2 is-flex is-justify-content-space-between is-align-items-center">
      <h3 class="is-size-3">{{ items.question }}</h3>
      <figure class="image is-32x32">
        <button @click="limit++">
          <img src="../assets/plus.svg" alt="Carregar mais">
        </button>
      </figure>
    </div>
    <Answers :answers="items.answers" :limit="limit" />
  </div>
</template>
<script setup lang="ts">
import Answers from "./Answers.vue";
import { ref } from "vue";

interface Props {
  items: {
    question: string;
    answers: string[];
  };
}

defineProps<Props>();

const limit = ref(1);
</script>
<style scoped>
.qa-container {
  background: var(--white-tone-secondary);
  border-radius: 1rem;
}

h3 {
  font-weight: 300;
  color: var(--purple-tone-strong);
}

button {
  outline: none;
  background-color: none;
  border: none;
  border-radius: 0.5rem;
  transition: 0.225s;
}

button:hover {
  transform: scale(1.225);
}

</style>