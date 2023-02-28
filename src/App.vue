<template>
  <div id="app">
    <VueCanvasCompression
      @getOriginal="getOriginal"
      @success="success"
      @error="error"
    />
  </div>
</template>

<script>
import VueCanvasCompression from './components/VueCanvasCompression'

export default {
  name: 'app',
  components: {
    VueCanvasCompression
  },
  methods: {
    getOriginal: function (file) {
      console.log('getOriginal', file);
    },
    success(file) {
      console.log('success', file);
    },
    error(e) {
      console.log(e);
    }
  },
}
</script>

<style>
</style>
