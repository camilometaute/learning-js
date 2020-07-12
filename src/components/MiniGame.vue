<template>
  <div>
    <h2>Mini Game</h2>
    My Health is: {{playerHealth}} <br>
    monsterHealth: {{monsterHealth}}
    <br>
    <button @click="startGame">Start Game</button>
    <button @click="attack">Atacalo</button>
  </div>
</template>

<script>
export default {
  name: 'VueDom',
  data: function() {
    return {
      playerHealth: 100,
      monsterHealth: 100,
      gameIsRunning: false
    }
  },
  computed: {

  },
  watch: {

  },
  methods: {
    startGame: function() {
      this.gameIsRunning = true;
      this.playerHealth = 100;
      this.monsterHealth = 100;
    },
    attack: function() {
      let max = 10;
      let min = 2;
      let damage = Math.max(Math.floor( Math.random() * max) + 1, min)
      this.monsterHealth -= damage;

      if (this.monsterHealth <= 0) {
        alert('you won')
        this.gameIsRunning = false;
        return;
      }

      max = 12;
      min = 5;
      damage = Math.max(Math.floor(Math.random() * max) +1, min)
      this.playerHealth -= damage;

      if (this.playerHealth <= 0) {
        alert('You Lost');
        this.gameIsRunning = false;
      }

    },
    specialAttack: function() {

    },
    health: function() {

    },
    giveUp: function() {

    }
  }
}
</script>
