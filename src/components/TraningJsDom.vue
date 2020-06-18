<template>
  <div>
    <span style="display: block">Training vue DOM
    {{sayHello()}}</span>

    <br>
    <button v-on:click="decrease(5)">-</button>
    <button v-on:click="reset">Reset</button>
    <button v-on:click="increase(5)">+</button>
    <p>{{counter}}</p>
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
      y: 0
    }
  },
  methods: {
    sayHello: function() {
      return this.hello;
    },
    increase: function(value) {
      this.counter += value;
    },
    decrease: function(value) {
      this.counter -= value;
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
