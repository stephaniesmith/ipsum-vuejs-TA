<template>
    <div id="app">
        <img src="./assets/logo.png">
        <IpsumList v-bind:selected="selected" v-on:selected="updatedSelected"/>
        <IpsumViewer v-bind:ipsum="selected" />
    </div>
</template>

<script>
import IpsumList from './components/IpsumList.vue'
import IpsumViewer from './components/IpsumViewer.vue'

export default {
    data() {
        return { selected: null };
    },
    components: {
        IpsumList,
        IpsumViewer
    },
    methods: {
        updatedSelected(ipsum) {
            this.selected = ipsum;
        }
    }
}
</script>

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
