<template>
    <div id="ipsumList">
        <h1>Ipsum List</h1>
        <ul>
            <li
                v-for="ipsum in ipsums"
                v-bind:key="ipsum.title"
                v-bind:class="{ selected: selected === ipsum }"
                v-on:click="$emit('selected', ipsum)"
            >
                {{ipsum.title}}
            </li>
        </ul>
    </div>
</template>

<script>
    import ipsums from '../data/ipsums';

    export default {
        data() {
            return { ipsums };
        },
        props: ['selected']
    }
</script>

<style>
#ipsumList {
   background-color: black;
   color:  white;
}
</style>