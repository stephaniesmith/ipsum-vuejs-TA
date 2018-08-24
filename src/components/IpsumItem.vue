<template>
  <li
    :class="{ selected: ipsum === selected }"
    @click="handleClick"
  >
    {{ipsum.title}}
  </li>
</template>

<script>
export default {
  props: ['ipsum', 'selected', 'onSelect'],
  methods: {
    handleClick() {
      this.onSelect(this.ipsum);
    }
  }
};
</script>

<style>
  li {
    background-color: white;
    color: black;
    padding: 1em;
    border-radius: .75em;
  }
</style>