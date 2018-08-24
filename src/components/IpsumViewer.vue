<template>
	<div id="ipsumViewer">
		<article v-if="ipsum">
      <p v-if="!editing">
        <button @click="editing = true">Edit</button>
      </p>
      <IpsumForm v-if="editing"
        :ipsum="ipsum"
        :onUpdate="handleUpdate"
        :onCancel="handleEndEdit"
      />
			<IpsumDisplay v-else :ipsum="ipsum"/>
		</article>
		<p v-else>Please select an ipsum</p>
	</div>
</template>

<script>
import IpsumDisplay from './IpsumDisplay.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  props: ['ipsum', 'onUpdate'],
  data: function() {
    return { 
      editing: false
    };
  },
  watch: {
    ipsum(newIpsum, oldIpsum) {
      if(newIpsum !== oldIpsum) this.editing = false;
    }
  },
  components: {
    IpsumDisplay,
    IpsumForm
  },
  methods: {
    handleEndEdit() {
      this.editing = false;
    },
    handleUpdate(ipsum) {
      console.log('here!');
      this.onUpdate(ipsum);
      this.handleEndEdit();
    }
  }
};
</script>

<style>
  #ipsumViewer {
    color:  grey;
    padding: 0 2rem;
	}
</style>