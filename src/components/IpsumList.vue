<template>
  <div id="ipsumList">
    <h1>Ipsum List</h1>
    <select v-on:change="$emit('selected', ipsums.filter(({ title }) => title === $event.target.value)[0])"
>
      <option>Select Ipsum</option>
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
    display: flex;
    align-items: center;
    background-color: grey;
    color:  white;
    justify-content: space-around;
    margin-bottom: 1.5rem;
    height: 2rem;
}

h1 {
    font-weight: bold;
    margin: .25em 0;
}

select {
    background-color: white;
    height: fit-content;
    padding: .25em;
    text-align-last: center;
}
</style>