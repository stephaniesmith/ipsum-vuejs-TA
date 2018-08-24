<template>
    <ul id="ipsumList">
      <IpsumItem
        v-for="ipsum in ipsums"
        :key="ipsum.key"
        :ipsum="ipsum"
        :selected="selected"
        :onSelect="onSelect"
      />
    </ul>
</template>

<script>
import IpsumItem from './IpsumItem.vue';

export default {
  props: ['ipsums', 'onSelect', 'selected'],
  components: {
    IpsumItem
  }
};
</script>

<style>
#ipsumList {
    padding: 2em;
    display: grid;
    background-color: grey;
    margin-bottom: 1.5rem;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    grid-gap: 20px;
}
</style>