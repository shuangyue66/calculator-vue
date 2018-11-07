<template>
  <div id="app">
    <base-layout></base-layout>
  </div>
</template>

<script>
import baseLayout from './components/base-layout.vue'

export default {
  name: 'app',
  components: {
   baseLayout
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
  width: 545px;
  height: 960px;
}
</style>
