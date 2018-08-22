<template>
  <div id="ipsums">
    <main>
      <IpsumList 
        :ipsums="ipsums"
        :selected="selectedIpsum"
        :onSelect="handleSelect"
      />
      <IpsumViewer 
        :ipsum="selectedIpsum"
      />
    </main>
  </div>
</template>

<script>
import ipsums from '../data/ipsums';
import IpsumList from './IpsumList.vue'
import IpsumViewer from './IpsumViewer.vue'

export default {
  data() {
    return {
      ipsums: ipsums,
      selectedIpsum: null 
      };
  },
  components: {
    IpsumList,
    IpsumViewer
  },
  methods: {
    handleSelect(ipsum) {
        this.selectedIpsum = ipsum;
    }
  }
}
</script>

<style>

</style>