<template>
  <div class="qa-container column m-6">
    <div class="mt-2 is-flex is-justify-content-space-between is-align-items-center">
      <h3 class="is-size-3">{{ items?.question }}</h3>
      <figure class="image is-32x32">
        <button @click="limit++">
          <img src="../assets/plus.svg" alt="Carregar mais">
        </button>
      </figure>
    </div>
    <AnswerInputVue @submit-answer="pushAnswer" />
    <p class="is-size-6" v-for="(answer, index) in limitedAnswers" :key="index">
      {{ answer }}
    </p>
  </div>
</template>
<script setup lang="ts">
import { ref, computed } from "vue";
import AnswerInputVue from "./AnswerInput.vue";

interface Props {
  items: {
    question: string;
    answers: string[];
  };
}

function pushAnswer(answer: string) {
  props.items.answers.push(answer)
}

const limitedAnswers = computed(() => {
  return props.items.answers.slice(0, limit.value);
});


const props = defineProps<Props>();

const limit = ref(2);
</script>
<style scoped>
.qa-container {
  background: var(--white-tone-secondary);
  border-radius: 1rem;
  cursor: pointer;
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