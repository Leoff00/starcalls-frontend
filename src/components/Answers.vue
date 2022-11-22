
<template>
  <p class="is-size-6" v-for="(a, index) in limitedAnswers" :key="index">
    {{ a }}
  </p>
</template>
<script setup lang="ts">

import { computed } from "vue";

interface Props {
  answers: string[];
  limit: number;
}
const props = defineProps<Props>();

const limitedAnswers = computed(() => {
  return props.answers.slice(0, props.limit);
});

</script>
<style scoped>
p {
  font-weight: 400;
  color: var(--soft-black-weakest);
}
</style>
