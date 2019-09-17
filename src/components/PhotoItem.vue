<template>
  <div class="photo-item">
    <img 
      :src='photo.urls.regular' 
      :alt='photo.alt_description'
      class='single-image'
    /> 
  </div>
</template>

<script>
export default {
  name: 'PhotoItem',
  props: ['photo']
}
</script>

<style scoped>
  .single-image {
  height: 500px;
  margin: 25px;
  object-fit: cover;
  min-width: 300px;
  max-width: 650px;
  box-shadow: 1px 1px 10px;
  }

</style>