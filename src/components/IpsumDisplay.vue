<template>
  <div>
    <h2>{{ipsum.title}}</h2>
			<p id="author">
				Posted on {{ipsum.publishedOn}} in {{ipsum.category}}
				by <a :href="ipsum.authorUrl">{{ipsum.author}}</a>
			</p>
		<div id="body" v-html="ipsum.body"></div>
  </div>
</template>

<script>
export default {
  props: ['ipsum']
};

</script>

<style scoped>
	h2 {
		font-size: 1.75em;
		font-weight: bold;
	}
  
	#author {
		font-weight: bold;
		margin: 1rem 0;
	}

	#body p {
		margin-bottom: .75rem;
	}

	#body img {
		margin: 1rem 0;
		width: 100%;
	}
</style>