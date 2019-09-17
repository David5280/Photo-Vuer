<template>
  <div class="photo-item">
    <img 
      :src="photo.urls.regular" 
      :alt="photo.alt_description"
      class='single-image'
    /> 
  </div>
</template>

<script>
export default {
  name: "PhotoItem",
  props: ["photo"]
}
</script>

<style scoped>

  .single-image {
  width: 350px;
  height: 600px;
  object-fit: cover;
  }
  
</style>