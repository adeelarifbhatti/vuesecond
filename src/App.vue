<template>
  <h1>
    {{title}}
    <input type="text" ref="name">
    <button @click="handleClick"> Click Me </button>
  </h1>
  <First header="this is for testing props" :text="text" theme="sale"/>

</template>

<script>
import First from './components/FirstComponent.vue'

export default {
  name: 'App',
  components: { First },
  data() {
    return {
      title: "First Vue app",
      text: "from data binding"
    }
  },
  methods: {
    handleClick(){
      this.$refs.name.classList.add('active')

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
  padding-bottom: 10px;
}
</style>
