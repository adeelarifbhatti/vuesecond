<template>
  <div v-if="showFirst">
    <h1>  
      {{title}}    
      <input type="text" ref="name">
      <button @click="handleClick"> Click Me </button>    
    </h1>
    <First header="this is for testing props" :text="text" theme="sale" @close="showFirstComponent"/>
  </div>
  <button @click="showFirstComponent" v-if="!showFirst"> open </button>
</template>

<script>
import First from './components/FirstComponent.vue'

export default {
  name: 'App',
  components: { First },
  data() {
    return {
      title: "First Vue app",
      text: "from data binding",
      showFirst: false
    }
  },
  methods: {
    handleClick(){
      this.$refs.name.classList.add('active')

    },
    showFirstComponent(){
      this.showFirst= !this.showFirst;
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
h1 {
  border-bottom: 3px solid rgb(141, 40, 40);
  display: inline-block;
  padding-bottom: 1px;
}
</style>
