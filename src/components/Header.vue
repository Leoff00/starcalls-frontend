<template>
   <header>
    <div class="header-container">
        <div class="logo-container">
            <img src="../assets/logo.svg" alt="Logo Header">
            <div class="text-container">
                <h3>Starcalls</h3>
                <h4>Making the right way</h4>
            </div>
        </div>
        <nav>
            <a target="#">About</a>
            <a target="#">Contact</a>
            <a target="#">Q&A's</a>
        </nav>
    </div>
    <Banner title="Help and Q&A Forums" />
</header>

</template>
<script lang="ts">
import { defineComponent } from 'vue';
import Banner from './Banner.vue';

export default defineComponent({
    name: "Header",
    components: { Banner }
})
</script>
<style scoped>
    header {
       background-color: var(--white-tone-header);
       height: 280px;

    }

    .header-container {
       display: flex;
       align-items: center;
       justify-content: space-evenly;
    }

    .logo-container {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    h3 {
        font-weight: 700;
    }
    .text-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    img {
        width: 80px;
        height: 80px;
    }

    a {
        margin: 0px 1.5rem;
        color: var(--dark-black-regular);
    }

</style>