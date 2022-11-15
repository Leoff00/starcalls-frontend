<template>
    <section>
        <div class="section-header">
            <h2>Questions & answers</h2>
        </div>

        <div v-for="(items) in data.qa" :key="items.q_id" class="qa-container">
            <h3>{{ items.question }}</h3>
            <p>{{ items.answer }}</p>
        </div>
    </section>
</template>
<script lang="ts" setup>
import { data } from "../mock/mock.json"


</script>
<style scoped>
.section-header {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 2rem;
}

.qa-container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

h2 {
    font-weight: 600;
    font-size: 2rem;
    color: var(--soft-black-weak);
}

h3 {
    font-size: 2.4rem;
    font-weight: 300;
    color: var(--purple-tone-strong);
}

p {
    font-weight: 400;
    color: var(--soft-black-weakest);
}
</style>