<template>
<h1> Hello World</h1>
<button @click="start" :disabled="isPlaying"> Start </button> 
<Attempt v-if="isPlaying" :delay="delay" @end="finish" />
<Output v-if="gameOver" :score="score" />
</template>

<script>
import  Attempt from './components/Attempt.vue'
import  Output from './components/Output.vue'
export default {
  name: 'App',
  components:

   { Attempt, Output },

data() {
    return {
      isPlaying: false,
      gameOver: false,
      delay: null,
      score: null
    }
  },
  methods: {
      start (){
        this.delay = 2000 + Math.random() * 5000
        this.isPlaying = true
        console.log(this.delay);
        this.gameOver = false
      },
        finish(finishTime){
          this.score = finishTime;
          console.log("running finish ", this.score);
          this.gameOver = true
          this.isPlaying = false
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
  color: #444;
  margin-top: 60px;
}
</style>
