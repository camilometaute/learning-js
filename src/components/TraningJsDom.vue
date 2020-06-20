<template>
  <div>
    <span style="display: block">Training vue DOM
    {{sayHello()}}</span>

    <br>
    <button v-on:click="counter--">-</button>
    <button v-on:click="counter = 0">Reset</button>
    <button v-on:click="counter++">+</button>
    <p>{{counter}}</p>
    <p>{{checkResult()}}</p>
    <br>
    <div
      style="width: 100%; height: 30vh;background-color: #fafafa; display: flex; align-items: center; justify-content:center; flex-direction: column; font-size: 2.6rem;"
      v-on:mousemove="updateCoordinates">
      <p style="margin: 1rem 0 2rem 0;">Coordinates {{x}} {{y}}</p>
      <span
        style="background-color: pink;"
        v-on:mousemove.stop="">
        Stop here coordinates</span>
        <!-- listening keyboard events -->
    </div>
    <input type="text" name="" placeholder="name" v-model="name">
    <p>{{name}}</p>
    <div class="colors-interactive">
      <div
        class="colors-interactive__box"
        @click="toggleColorRed = !toggleColorRed"
        :class="{'colors-interactive__red' : toggleColorRed}">
      </div>

      <div
        class="colors-interactive__box"
        @click="toggleColorBlue = !toggleColorBlue"
        :class="{'colors-interactive__blue' : toggleColorBlue}"
      >
      </div>

      <div
        class="colors-interactive__box"
        @click="toggleColorGreen = !toggleColorGreen"
        :class="{'colors-interactive__green' : toggleColorGreen }"
      >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VueDom',
  data: function() {
    return {
      name: '',
      hello: 'Hello world',
      link: 'http://google.com',
      counter: 0,
      x: 0,
      y: 0,
      toggleColorRed: false,
      toggleColorBlue: false,
      toggleColorGreen: false
    }
  },
  watch: {
    counter: function() {
      let vueInstance = this;
      setTimeout(function(){
        vueInstance.counter = 0
      }, 3000);
    }
  },
  methods: {
    sayHello: function() {
      return this.hello;
    },
    checkResult: function() {
      return this.counter > 5 ? 'Great' : 'Bad'
    },
    reset: function() {
      this.counter = 0;
    },
    updateCoordinates: function(event) {
      this.x = event.clientX;
      this.y = event.clientY;
    }
  }
}
</script>
