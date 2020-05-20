<template>
  <div id="app">
    <h2>Training JS with objects {{person.role}} {{person.name}} {{person.age}} {{person.bikes.moto1}} {{person.bikes.moto2}}</h2>
    <TypeAutomatic/>
    <HelloWorld msg="Descarga este documento"/> <br>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TypeAutomatic from './components/TypeAutomatic.vue'

export default {
  name: 'app',
  data: function() {
    return {
      person: {
        name: 'Camilo',
        role: 'Designer',
        age: 30,
        bikes: {
          moto1 : 'Yamaha',
          moto2 : 'Hero'
        }
      }
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
