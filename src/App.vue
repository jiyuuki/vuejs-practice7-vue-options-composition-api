<template>
    <select v-model="componentName">
        <option value="vueOptions">Vue Options Api</option>
        <option value="vueComposition">Vue Composition Api</option>
    </select>

    <keep-alive>
        <component :is="componentName"></component>
    </keep-alive>

</template>

<script>
import vueOptions from "./components/vueOptions.vue"
import vueComposition from "./components/vueComposition.vue"

export default {
    name: "App",
    components: {
        vueOptions,
        vueComposition,
    }, 
    data () {
        return {
            componentName: "vueOptions"
        }
    }
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
