<template>
  <div>
    <h2>Bikes</h2>
    
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
