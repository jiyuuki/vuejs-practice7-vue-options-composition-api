<template>
    <vueOptions />
</template>

<script>
import vueOptions from './components/vueOptions.vue'
// import vueComposition from "./components/vueComposition.vue";
export default {
    components: {
        vueOptions,
        // vueComposition,
    },
};
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
