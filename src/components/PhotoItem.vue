<template>
    <img 
      :src='photo.urls.regular' 
      :alt='photo.alt_description'
      class='single-image'
    /> 
</template>

<script>
export default {
  name: 'PhotoItem',
  props: ['photo']
}
</script>

<style scoped>
.photo-item {
  width: 100%;
}
  .single-image {
  width: 100%;
  object-fit: cover;
  max-width: 600px;
  box-shadow: 1px 1px 10px;
  }

</style>