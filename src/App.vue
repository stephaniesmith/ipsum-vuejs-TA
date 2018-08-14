<template>
    <div id="app">
        <header>
            <img src="./assets/logo.png">
            <h1>Steph Learns Vue!</h1>
        </header>
        <main>
            <IpsumList v-bind:selected="selected" v-on:selected="updatedSelected"/>
            <IpsumViewer v-bind:ipsum="selected" />
        </main>
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
    color: #2c3e50;
}

header {
    display: flex;
    align-items: center;
    padding: 2rem;
}
header img {
    width: 5rem;
    object-fit: contain;
    margin-right: 1rem;
}

header h1 {
    font-weight: bolder;
    font-size: 1.25em;
}
</style>
