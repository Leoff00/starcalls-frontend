<template>
    <div>
        <h1>
            {{ title }}
        </h1>
    </div>

</template>
<script setup lang="ts">

const props = defineProps({title: String})

</script>
<style scoped>
    div {
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 2rem;
    }

    h1 {
        filter: drop-shadow(1px 0px 8px rgb(170, 170, 170));
        font-size: 3.8rem;
        color: var(--red-tone-weak);
        font-weight: 700;
    }
</style>