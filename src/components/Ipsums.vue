<template>
  <div id="ipsums">
    <main>
      <AddIpsum 
        :onAdd="handleAdd"
      />
      <IpsumList 
        :ipsums="ipsums"
        :selected="selectedIpsum"
        :onSelect="handleSelect"
      />
      <IpsumViewer 
        :ipsum="selectedIpsum"
        :onUpdate="handleUpdate"
      />
    </main>
  </div>
</template>

<script>
import ipsums from '../data/ipsums';
import IpsumList from './IpsumList.vue';
import IpsumViewer from './IpsumViewer.vue';
import AddIpsum from './AddIpsum.vue';

export default {
  data() {
    return {
      ipsums: ipsums,
      selectedIpsum: null 
    };
  },
  components: {
    IpsumList,
    IpsumViewer,
    AddIpsum
  },
  methods: {
    handleAdd(ipsum) {
      this.ipsums.push(ipsum);
    },
    handleSelect(ipsum) {
      this.selectedIpsum = ipsum;
    },
    handleUpdate(updated) {
      const index = this.ipsums.findIndex(ipsum => ipsum.key === updated.key);

      if(index !== -1) {
        this.ipsums.slice(index, 1, updated);
        this.selectedIpsum = updated;
      }
    }
  }
};
</script>

<style>

</style>