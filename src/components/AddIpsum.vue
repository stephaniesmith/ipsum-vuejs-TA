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