<template>
    <section>
        <div class="mt-2 is-flex is-justify-content-center is-align-items-center">
            <h2 class="is-size-3">Questions & answers</h2>
        </div>
        <section v-for="items in data" :key="items.q_id" class="container">
            <div class="qa-container column m-6">
                <div class="mt-2 is-flex is-justify-content-space-between is-align-items-center">
                    <h3 class="is-size-3">{{ items.question }}</h3>
                    <figure class="image is-32x32">
                        <button @click="limit++">
                            <img src="../assets/plus.svg" alt="Carregar mais">
                        </button>
                    </figure>
                </div>
                <!-- <div class="pb-1 pt-2" v-for="answer in range"> -->
                <p class="is-size-6" v-for="a in range" :key="items.q_id">{{ a }}</p>
                <!-- </div> -->
            </div>
        </section>
    </section>
</template>
<script lang="ts" setup>
import { ref, computed } from "vue";
import { data } from "../mock/mock.json"
const limit = ref(2)

const answers = data.map((v) => v.answers)

const range = computed(() => {
    return answers.slice(0, limit.value)
})

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

h2 {
    font-weight: 600;
    color: var(--soft-black-weak);
}

h3 {
    font-weight: 300;
    color: var(--purple-tone-strong);
}

p {
    font-weight: 400;
    color: var(--soft-black-weakest);
}
</style>