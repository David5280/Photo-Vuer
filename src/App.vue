<template>
  <div id="app">
    <Photos />
  </div>
</template>

<script>
import Photos from './components/Photos'

export default {
  name: 'app',
  components: {
    Photos
  },
  data() {
    return {
      
    }
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
