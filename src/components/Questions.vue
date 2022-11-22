<template>
    <section>
        <div class="mt-2 is-flex is-justify-content-center is-align-items-center">
            <h2 class="is-size-3">Questions & answers</h2>
        </div>
        <section v-for="items in data" :key="items.q_id" class="container">
            <Question :items="items" />
        </section>
    </section>
</template>
<script lang="ts" setup>
import { data } from "../mock/mock.json"
import Question from "./Question.vue"
</script>
<style scoped>

h2 {
    font-weight: 600;
    color: var(--soft-black-weak);
}



</style>