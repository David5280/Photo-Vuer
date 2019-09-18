<template>
  <div id="app">
    <Header @search:query='searchPhotos'/>
    <Photos v-bind:photos="photos" />
    
  </div>
</template>

<script>
import Header from './components/Header';
import Photos from './components/Photos';

const API_KEY=process.env.VUE_APP_API_KEY

export default {
  name: 'app',
  components: {
    Photos,
    Header
  },
  data() {
    return {
      photos: null
    }
  },
  mounted() {
    fetch(`https://api.unsplash.com/photos/?per_page=48&client_id=${API_KEY}`)
    .then(res => res.json())
    .then(data => (this.photos = data))
    .catch(err => err)
  },
  methods: {
    searchPhotos(query) {
      fetch(`https://api.unsplash.com/search/photos?page=1&per_page=48&query=${query}&client_id=${API_KEY}`)
      .then(res => res.json())
      .then(data => (this.photos = data.results))
      .catch(err => err)
    }
  },
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: 'Apple Chancery', Helvetica, sans-seriff;
    line-height: 1.4;
    background: rgb(134, 134, 134);

  }
</style>
