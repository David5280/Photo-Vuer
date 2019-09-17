<template>
  <div id="app">
    <Photos v-bind:photos="photoData"/>
    
  </div>
</template>

<script>
import { getPhotos } from './Utils/ApiCalls/ApiCalls'
import { apiKey } from './Utils/ApiCalls/apiKey'
import Photos from './components/Photos'

export default {
  name: 'app',
  components: {
    Photos
  },
  data() {
    return {
      photoData: null
    }
  },
  mounted() {
  fetch(`https://api.unsplash.com/photos/?client_id=${apiKey}`)
  .then(res => res.json())
  .then(data => (this.photoData = data))
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
  }
</style>
