<template>
    <vueOptions/>
</template>

<script>
    import vueOptions from './components/vueOptions.vue'

    export default {
        name: 'App',
        components: {
            vueOptions
        }
    }
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
