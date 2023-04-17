<template>
  <div id="app">
    <SamlSample />
  </div>
</template>

<script>
import SamlSample from './components/SamlSampleView.vue'

export default {
  name: 'App',
  components: {
    SamlSample
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
