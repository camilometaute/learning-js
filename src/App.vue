<template>
  <div id="app">
    <h4>Larning map with JS <span @click="mapElement">mapElement</span> </h4>
    <TypeAutomatic/>
    <HelloWorld msg="Descarga este documento"/> <br>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TypeAutomatic from './components/TypeAutomatic.vue'

export default {
  name: 'app',
  methods: {
    mapElement() {
      // set
      const score = 200;

      const myScore = new Map();

      myScore.set(100, 'Downhill bike')
      myScore.set(200, 'Road bike')
      myScore.set(300, 'Naked bike')
      myScore.set(400, 'Motocross bike')

      alert(`you win a ${myScore.get(score)} with a score of ${score}`)

      // has
      // delete
    }
  },
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
