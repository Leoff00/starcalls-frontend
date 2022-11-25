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
    q_id: number;
    question: string;
    answers: Array<string>;
}

const recData = ref<Array<QAProps>>([])

function pushData(question: string) {
    recData?.value?.push({ q_id: 1, question, answers: [''] })
}

</script>
