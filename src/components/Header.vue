<template>
  <div class='header'>
    <h1>
      PHOTO-VUER
    </h1>
    <form 
      class='search-box'
      @submit.prevent='handleSubmit'
    >
      <input 
        type='text' 
        placeholder='Search...'
        class='form-input'
        v-model='search.query'
      />
      <button class='form-input'>Search</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      search: {
        query: '',
      }
    }
  },
  methods: {
    handleSubmit() {
      this.$emit('search:query', this.search.query)
    }
  }
}
</script>

<style scoped>
  .header {
    display: grid;
    grid-template-columns: 20% 60% 20%;
    border-bottom: 2px solid black;
  }
  h1 {
    text-align: center;
    grid-column-start: 2;
    grid-column-end: 3;
    font-size: 3rem;
  }
  form {
    margin: auto;
    grid-column-start: 3;
    grid-column-end: 4;
  }
  .form-input {
    height: 35px;
  }
</style>