<template>
	<div id="ipsumViewer">
		<article v-if="ipsum">
      <IpsumForm/>
			<IpsumDisplay :ipsum="ipsum"/>
		</article>
		<p v-else>Please select an ipsum</p>
	</div>
</template>

<script>
import IpsumDisplay from './IpsumDisplay.vue';
import IpsumForm from './IpsumForm.vue';

export default {
  data: function() {
    return { 
      editing: false
    };
  },
  components: {
    IpsumDisplay,
    IpsumForm
  },
  props: ['ipsum']
};
</script>

<style>
  #ipsumViewer {
   	color:  grey;
		padding: 0 2rem;
	}
</style>