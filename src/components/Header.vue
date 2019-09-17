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
      <button class='form-input' :disabled="this.search.query.length >= 1 ? disabled : ''">
        <img src='../assets/search.png' class='form-input'/>
      </button>
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
      this.search.query = '';
    }
  }
}
</script>

<style scoped>
  .header {
    display: grid;
    grid-template-columns: 20% 60% 20%;
    border-bottom: 2px solid black;
    background: rgb(134, 134, 134);
    box-shadow: 2px 2px 10px;
    position: fixed;
    top: 0;
    height: 75px;
    width: 100%
  }
  h1 {
    text-align: center;
    grid-column-start: 2;
    grid-column-end: 3;
    font-size: 2.5rem;
    margin: auto;
  }
  form {
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    grid-column-start: 3;
    grid-column-end: 4;
  }
  .form-input {
    height: 35px;
    margin: auto;
  }
</style>