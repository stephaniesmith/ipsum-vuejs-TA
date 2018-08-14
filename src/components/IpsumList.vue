<template>
    <div id="ipsumList">
        <h1>Ipsum List</h1>
        <select v-on:change="$emit('selected', ipsums.filter(({ title }) => title === $event.target.value)[0])"
>
            <option
                v-for="ipsum in ipsums"
                v-bind:key="ipsum.title"
                v-bind:class="{ selected: selected === ipsum }"
            >
                {{ipsum.title}}
            </option>
        </select>
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
   background-color: grey;
   color:  white;
}
select {
    background-color: white;
}
</style>