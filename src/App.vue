<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="He we will learn JS"/>
    <button v-on:click="reverseMessage" type="button" name="button">Hello world</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  methods: {
    reverseMessage: function () {

      //function scoped
      var firstVariable = 'This is the first variable'; //Can be updated

      //block scoped {}
      let age = 30; // Can be updated
      const sport = true; // Can't be updated

      //camel case
      const iLovePizza = true;

      //UpperCamelCase
      const ILoveToEatHotDogs = false;

      // snake case!!
      const this_is_snake_case = true;

      //kebab-case this is not allowed in javascrip

      alert( firstVariable + age + sport + ILoveToEatHotDogs + this_is_snake_case + iLovePizza);
    }
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
