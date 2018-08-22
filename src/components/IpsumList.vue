<template>
  <div id="ipsumList">
    <ul>
      <IpsumItem
        v-for="ipsum in ipsums"
        :key="ipsum.title"
        :ipsum="ipsum"
        :selected="selected"
        :onSelect="onSelect"
      />
    </ul>
  </div>
</template>

<script>
    import IpsumItem from './IpsumItem.vue';

    export default {
        // data() {
        //     return { ipsums };
        // },
        props: ['ipsums', 'onSelect', 'selected'],
        components: {
            IpsumItem
        }
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
}
</style>