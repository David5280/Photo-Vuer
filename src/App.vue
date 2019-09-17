<template>
  <div id="app">
    <Header />
    <Photos v-bind:photos="photos" />
    
  </div>
</template>

<script>
import { getPhotos } from './Utils/ApiCalls/ApiCalls';
import { apiKey } from './Utils/ApiCalls/apiKey';
import Header from './components/Header';
import Photos from './components/Photos';

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
  fetch(`https://api.unsplash.com/photos/?client_id=${apiKey}`)
  .then(res => res.json())
  .then(data => (this.photos = data))
  .catch(err => err)
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-seriff;
    line-height: 1.4;
    background: #ccc;
  }
</style>
