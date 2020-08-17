<template>
  <div id="app">
    <h4>Larning map with JS <span @click="mapElement">mapElement</span> </h4>
    <PasswordValidate/>
    <MiniGame/>
    <TraningJsDom/>
    <TypeAutomatic/>
    <HelloWorld msg="Descarga este documento"/> <br>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TypeAutomatic from './components/TypeAutomatic.vue'
import TraningJsDom from './components/TraningJsDom.vue'
import MiniGame from './components/MiniGame.vue'
import PasswordValidate from './components/PasswordValidate.vue'

export default {
  name: 'app',
  methods: {
    sayHello: function() {
      return this.title;
    },
    mapElement() {
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
    TypeAutomatic,
    TraningJsDom,
    MiniGame,
    PasswordValidate
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
