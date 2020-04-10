<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <label for="">Ingresa la contraseña</label> <br>
    <input v-model="inputPassword" type="password" name="" value=""> <br>
    <button :disabled="validatePassword(inputPassword)" @click="goToNewUrl(inputPassword)" type="button" name="button">
      Descargar documento
    </button>
    <button :disabled="validatePassword(inputPassword)" @click="goToNewUrl(inputPassword)" type="button" name="button">
      Descargar documento 2
    </button>
    <button :disabled="validatePassword(inputPassword)" @click="goToNewUrl(inputPassword)" type="button" name="button">
      Descargar documento 3
    </button>
    <button :disabled="validatePassword(inputPassword)" @click="goToNewUrl(inputPassword)" type="button" name="button">
      Descargar documento 4
    </button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function () {
    return {
      inputPassword: ''
    }
  },
  methods: {
    validatePassword(password) {
      if (password != 'Camilo') {
        return true;
      }
      else if (password != 'Camilo') {
        return false;
      }
    },
    goToNewUrl (password) {
      if (password === 'Camilo') {
        window.location.href = 'https://vuejs.org/v2/guide/components.html'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
