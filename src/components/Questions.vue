
// ! FIX
<template>
    <section>

        <Input @new-q="data.push()" />
        <section v-for="items in data" :key="items.q_id" class="container">
            <Question :items="items" />
        </section>
    </section>
</template>
<script lang="ts" setup>
import { data } from "../mock/mock.json"
import Question from "./QandA.vue"
import Input from "./Input.vue";
</script>
