<template>
  <div>
    <div v-if="hiddenElement">
      <h4>Element to toggle 1</h4>
      <h5>Element to toggle 2</h5>

    </div>
    <button @click="hiddenElement = !hiddenElement">Toggle Event</button>
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
        :class="InputColor"
      >
      </div>

      <div
        class="colors-interactive__box"
        @click="toggleColorGreen = !toggleColorGreen"
        :class="toggleClasses"
      >
      </div>
      <div
        class="colors-interactive__box"
        :style="myStyle"
      >
      </div>
    </div>
    <input placeholder="Which color do you want" v-model="InputColor">
    <input placeholder="Which width" v-model="width">
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
      toggleColorGreen: false,
      InputColor : '',
      width : 40,
      hiddenElement: true,
      names: [
        {name: 'camilo', age: 31, color: 'Yellow'},
        {name: 'Cristhian', age: 32, color: 'Blue'},
        {name: 'El MIlo', age: 33, color: 'Red'}
      ],
      bikes: [
        {type: 'Naked', cc: '850cc', color: 'gray', brand: 'MT 09'},
        {type: 'Motocross', cc: '125cc', color: 'blue', brand: 'YZ'},
        {type: 'Sport', cc: '99cc', color: 'gray/black', brand: 'Eco Deluxe'},
      ]
    }
  },
  computed: {
    toggleClasses: function() {
      return {
        'colors-interactive__green' : this.toggleColorGreen
      }
    },
    myStyle: function() {
      return {
        backgroundColor : this.InputColor,
        flex : '0 0' + this.width + '%'
      };
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
