<template>
  <form class="d-flex" @submit.prevent="$emit('search')">
    <select
      class="form-select"
      aria-label="Default select example"
      name="genere"
      id="genere"
      @input="$emit('input', $event.target.value)"
      @keyup="$emit('search', searchText)"
    >
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </form>
</template>

<script>
export default {
  name: "searchText",
    
    
  props:{
      searchText = String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
</style>