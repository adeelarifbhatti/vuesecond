<template>
  <div   v-if="showFirst">
     <!-- {{title}}    
      <input type="text" ref="name">
      <button @click="handleClick"> Sign in </button>   
      --> 
    
    <First header="this is for testing props" :text="text" theme="sale" @close="showFirstComponent">
      
      <p> Signing Up  </p>
      <template v-slot:links>
        
      </template>
    </First>
  </div>
<!-- ############################################################################################### -->
  <div   v-if="showFirst2">
    <First header="this is for testing props" :text="text" theme="sale" @close="showFirstComponent2">
      
      <p> Signing in  </p>
      <template v-slot:links>
        
      </template>
    </First>
  </div>


  <button @click="showFirstComponent" v-if="!showFirst"> SignUp </button>
   <button @click="showFirstComponent2" v-if="!showFirst2"> SignIn </button>
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
      showFirst: false,
      showFirst2: false
    }
  },
  methods: {
    handleClick(){
      this.$refs.name.classList.add('active')

    },
    showFirstComponent(){
      this.showFirst2= !this.showFirst2;
      this.showFirst= !this.showFirst2;
    },
        showFirstComponent2(){
      this.showFirst2= !this.showFirst2;
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
