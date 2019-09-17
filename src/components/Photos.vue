<template>
  <div>
    <div v-for="photo in photos">
      {{ photo }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Photos",
  props: [photoData]
}
</script>

<style scoped>

</style>