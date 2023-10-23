<template>
   <h1> reaction timer game </h1>
   <button @click="start" :disabled="isPlaying" >play</button>
   <Block v-if="isPlaying" v-bind:delay="delay"/>
</template>

<script>

import Block from "./components/Block.vue"
 
export default {
  name: 'App',
  components: { 
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true;
      console.log(this.delay)
    }
  }
}
</script>

<style>
#app {
  text-transform: capitalize;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #9d7b9d;
  margin-top: 60px;
}
button{
  border: none;
  padding: 1% 2%;
  margin: 2%;
  cursor: pointer;
  color: darkcyan;
  background-color: bisque;
  border-radius: 0.6rem;
  font-weight: bold;
}
</style>
