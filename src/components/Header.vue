<template>
  <div class='header'>
    <h1>
      PHOTO-VUER
    </h1>
    <form 
      @submit.prevent='handleSubmit'
    >
      <input 
        type='text' 
        placeholder='Search...'
        class='form-input'
        id='text-input'
        v-model='search.query'
      />
      <button 
        class='form-input' 
        id='search-btn'
        :disabled="!search.query"
      >
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
      },
    }
  },
  methods: {
    handleSubmit() {
      this.$emit('search:query', this.search.query)
      this.search.query = '';
    },
    toggleSearchBtn() {
      if (this.search.query.length >= 1) {
        this.searchBtn.disabled = !this.searchBtn.disabled
      }
    }
  }
}
</script>

<style scoped>
  .header {
    display: grid;
    grid-template-columns: 25% 50% 25%;
    border-bottom: 2px solid black;
    background: #ccc;
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
    font-size: 3rem;
    margin: auto;
  }
  form {
    margin:  auto auto auto 0px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    grid-column-start: 3;
    grid-column-end: 4;
    width: 100%;
    height: fit-content;
  }
  .form-input {
    height: 35px;
  }
  #text-input {
    width: 200px;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    border-top: 1px solid black;
    border-left: 1px solid black;
    border-bottom: 1px solid black;
  }
  #search-btn {
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    background: #FFF;
    border-top: 1px solid black;
    border-right: 1px solid black;
    border-bottom: 1px solid black;
  }
  #search-btn:hover {
    cursor: pointer;
  }
  @media (max-width: 700px) {
    .header {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    h1 {
      font-size: 2rem;
      margin: 0;
    }
    form {
      width: 175px;
      margin: 0;
    }
    .form-input {
      height: 25px;
    }
  }
</style>