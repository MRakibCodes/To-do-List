<template>
  <div id="app">
    <mainBody />
  </div>
</template>

<script>
import mainBody from './components/mainBody.vue'

export default {
  name: 'app',
  components: {
    mainBody
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
  padding-top: 40px;
}
</style>
