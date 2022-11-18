<template>
    <section>
        <div class="mt-2 is-flex is-justify-content-center is-align-items-center">
            <h2>Questions & answers</h2>
        </div>

        <article v-for="(items) in data.qa" :key="items.q_id" class="container">
            <div class="qa-container column m-6">
                <h3 class="is-size-3">{{ items.question }}</h3>
                <p class="is-size-6 pb-3 pt-2" v-for="(answer) in items.answers">{{ answer }}</p>
            </div>
        </article>
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
    background: var(--white-tone-secondary);
    border-radius: 1rem;
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