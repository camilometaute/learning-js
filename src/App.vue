<template>
  <div id="app">
    <TypeAutomatic/>
    <HelloWorld msg="Descarga este documento"/> <br>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TypeAutomatic from './components/TypeAutomatic.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    TypeAutomatic
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
  margin-top: 60px;
}
</style>
