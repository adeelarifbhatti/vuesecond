<template>
<h1> Hello World</h1>
<button @click="start" :disabled="isPlaying"> Start </button> 
<Attempt v-if="isPlaying" :delay="delay"/>
</template>

<script>
import  Attempt from './components/Attempt.vue'
export default {
  name: 'App',
  components:

   { Attempt },

  data() {
    return {
      isPlaying: false,
      delay: null
    }

  },
  methods: {
      start (){
        this.delay = 2000 + Math.random() * 50000
        this.isPlaying = true
        console.log(this.delay);
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
