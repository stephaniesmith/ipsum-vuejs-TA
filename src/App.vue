<template>
    <div id="app">
        <header>
            <img src="./assets/logo.png">
            <h1>Steph Learns Vue!</h1>
        </header>
        <Ipsums/>
    </div>
</template>

<script>
import Ipsums from './components/Ipsums.vue'

export default {
    components: {
        Ipsums
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
