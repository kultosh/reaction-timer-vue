<template>
  <h2>Vue Reaction Timer</h2>
  <button @click="start" :disabled="isplaying">Play</button>
  <Block v-if="isplaying" :delay="delay" @end="endGame" />
  <div>
    <p v-if="showResult">Reaction time: {{score}} ms </p>
  </div>
</template>

<script>
import Block from './components/Block.vue'

export default { 
  name: 'App',

  components: {
    Block
  },

  data () {
    return {
      isplaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },

  methods: {
    start () {
      this.delay = 2000 + Math.random() * 5000,
      this.isplaying = true
      this.showResult = false
    },

    endGame (reactionTimer) {
      this.score = reactionTimer
      this.showResult = true
      this.isplaying = false
      console.log(this.score)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
