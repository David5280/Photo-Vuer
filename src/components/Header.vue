<template>
  <div class='header'>
    <h1>
      PHOTO-VUER
    </h1>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
  .header {
    display: grid;
    grid-template-columns: 20% 60% 20%;
  }
  h1 {
    text-align: center;
    grid-column-start: 2;
    grid-column-end: 3;
    font-size: 3rem;
  }
</style>