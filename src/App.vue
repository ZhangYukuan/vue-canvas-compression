<template>
  <div id="app">
    <VueCanvasCompression
      @getOriginal="getOriginal"
      @success="success"
      @error="error"
      :preview="true"
      :width='200'
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
      console.log('原始图片信息', file);
    },
    success(file) {
      console.log('压缩后图片信息', file);
    },
    error(e) {
      console.log(e);
    }
  },
}
</script>

<style>
</style>
