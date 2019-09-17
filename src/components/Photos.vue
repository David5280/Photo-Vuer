<template>
  <div>
    <div v-bind:key="photo.id" v-for="photo in photos">
      {{ photo.urls.full }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Photos",
  props: ["photos"]
}
</script>

<style scoped>

</style>