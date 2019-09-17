<template>
  <div class="photos-container">
    <div 
      v-bind:key='photo.id' 
      v-for='photo in photos'
    >
      <PhotoItem v-bind:photo='photo'/>
    </div>
  </div>
</template>

<script>
import PhotoItem from './PhotoItem';

export default {
  name: 'Photos',
  components: {
    PhotoItem,
  },
  props: ['photos']
}
</script>

<style scoped>
  .photos-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 25px;
  }
</style>