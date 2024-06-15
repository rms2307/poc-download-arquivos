<template>
  <div id="app">
    <DownloadPdf />
  </div>
</template>

<script>
import DownloadPdf from './components/DownloadPdf.vue';

export default {
  name: 'App',
  components: {
    DownloadPdf
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
