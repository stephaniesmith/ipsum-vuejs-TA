<template>
  <form @submit.prevent="handleSubmit">
    <p>
      <label>
        Title: <input v-model="title">
      </label>
    </p>
    <p>
      <label>
        Category: <input v-model="category">
      </label>
    </p>
    <p>
      <label>
        Author: <input v-model="author">
      </label>
    </p>
    <p>
      <label>
        Website: <input v-model="authorUrl">
      </label>
    </p>
    <p>
      <label>
        Published Date: <input v-model="publishedOn">
      </label>
    </p>
    <p>
      <label>
        Body: <input v-model="body">
      </label>
    </p>
    <p>
      <button type="submit">Update</button>
      <button type="button" @click="onCancel">Update</button>
    </p>
  </form>
</template>

<script>
export default {
  props: ['ipsum', 'onUpdate', 'onCancel'],
  created() {
    const ipsum = this.ipsum;
    this.title = ipsum.title;
    this.category = ipsum.category;
    this.author = ipsum.author;
    this.authorUrl = ipsum.authorUrl;
    this.publishedOn = ipsum.publishedOn;
    this.body = ipsum.body;
  },
  methods:{
    handleSubmit() {
      const ipsum = {
        key: this.ipsum.key,
        title: this.title,
        category: this.category,
        author: this.author,
        authorUrl: this.authorUrl,
        publishedOn: this.publishedOn,
        body: this.body
      };
      this.onUpdate(ipsum);
    }
  }
};
</script>

<style scoped>

</style>