<template>
  <section class="column is-half">
    <input class="input" type="text" v-model="answerInput">
    <button class="button" @click="emit('submit-answer', answerInput)">Submit answer</button>
  </section>
</template>
<script lang="ts" setup>
import { ref } from 'vue';

const answerInput = ref("")
const emit = defineEmits<{ (e: 'submit-answer', answerInput: string): void }>()
</script>
