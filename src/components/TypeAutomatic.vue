<template>
  <div class="container">
    <h1>Coding is
      <span class="typed-text">{{ typeValue }}</span>
      <span class="cursor" :class="{'typing': typeStatus}">&nbsp;</span>
    </h1>
  </div>
</template>

<script>
export default {
  name: 'TypeAutomatic',
  data() {
    return {
      typeValue: '',
      typeStatus: false,
      typeArray: ['fun', 'awesome', 'a journey', 'life'],
      typingSpeed: 300,
      erasingSpeed: 100,
      newTextDelay: 2000,
      typeArrayIndex: 0,
      charIndex: 0
    }
  },
  methods: {
      typeText() {
        // si index es menor al .lenght de cada palabra
        if(this.charIndex < this.typeArray[this.typeArrayIndex].length) {
          // si es diferente a typeStatus
          if(!this.typeStatus)
          // cambiamos typeStatus por true
            this.typeStatus = true;

          // almacenamos en typeValue la primera letra de la primera palabra del array
          this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
          // sumamos a charIndex 1
          this.charIndex += 1;
          // con la velocidad de typingSpeed ejecuteme otra vez la función/metodo
          setTimeout(this.typeText, this.typingSpeed);
        }
        else {
          this.typeStatus = false;
          setTimeout(this.eraseText, this.newTextDelay);
        }
      },
      eraseText() {
        if(this.charIndex > 0) {
          if(!this.typeStatus)
            this.typeStatus = true;
          this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1);
          this.charIndex -= 1;
          setTimeout(this.eraseText, this.erasingSpeed);
        }
        else {
          // como ya borró, debería poner el status en false
          this.typeStatus = false;
          // suma 1 al tyleArrayIndex para recorrerlo
          this.typeArrayIndex += 1;
          // compara si el index del array es >= al lenght del array
          if(this.typeArrayIndex >= this.typeArray.length)
          // Si es >= 0 lo devuelve a 0
            this.typeArrayIndex = 0;
          setTimeout(this.typeText, this.typingSpeed + 1000);
        }
      }
    },
    created() {
      setTimeout(this.typeText, this.newTextDelay + 200);
    }
  }
</script>
