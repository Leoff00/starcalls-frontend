<template>
    <section>
        <Input @submitted="pushData" />
        <section v-for="items in recData" :key="items.q_id" class="container">
            <Question :items="items" />
        </section>
    </section>
</template>
<script lang="ts" setup>
import { ref } from "vue"
import Question from "./QandA.vue"
import Input from "./Input.vue";

interface QAProps {
    q_id: string;
    question: string;
    answers: Array<string>;
}

const recData = ref<Array<QAProps>>([])

function pushData(question: string): void {
    recData?.value?.push({ q_id: crypto.randomUUID(), question, answers: [''] })
    localStorage.setItem('questions', JSON.stringify(recData))
}

function showLocalStorage(): void {
    if (!recData) localStorage.getItem('questions')
}

</script>
