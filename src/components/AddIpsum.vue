<template>
  <form class="add" @submit.prevent="handleSubmit">
      <label>
        Title: <input v-model="title">
      </label>
      <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  props: ['onAdd'],
  data: function() {
    return {
      title: ''
    };
  },
  methods: {
    handleSubmit() {
      const newIpsum = {
        key: this.title,
        title: this.title
      };
      this.onAdd(newIpsum);
      this.title = '';
    }
  }
};
</script>

<style scoped>
  form.add {
    width: fit-content;
    margin: 0 auto;
    margin-bottom: 15px;
  }

  .add button {
    margin: 10px;
  }

</style>