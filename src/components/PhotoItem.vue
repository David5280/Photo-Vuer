<template>
  <div class="photo-item">
    <img :src="photo.urls.regular" /> 
  </div>
</template>

<script>
export default {
  name: "PhotoItem",
  props: ["photo"]
}
</script>

<style scoped>
  .photo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc solid;
  }
</style>