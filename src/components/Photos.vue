<template>
  <div class="photos-container">
    <div
      class="photo-wrapper"
      :key='photo.id' 
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
    margin-top: 90px;
    padding: 25px;
    column-count: 3;
  }
  .photo-wrapper {
    width: 100%;
  }
  @media (max-width: 1400px) {
    .photos-container {
      column-count: 4;
    }
  }
  @media (max-width: 700px) {
    .photos-container {
      column-count: 2;
    }
  }
  @media (max-width: 480px) {
    .photos-container {
      column-count: 1;
    }
  }

</style>