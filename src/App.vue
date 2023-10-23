<template>
   <h1> reaction timer game </h1>
   <button @click="start" :disabled="isPlaying"   >play</button>
   <Block v-if="isPlaying" :delay="delay"  @end="endGame" />  
   <!-- if we hashed this last unmounted will appear -->
   <!-- <p v-if="showResults">reaction time is : {{ score }}  ms </p> -->
   <Result  v-if="showResults" :score="score"  />
</template>

<script>

import Block from "./components/Block.vue"
import Result from "./components/Result.vue" 

export default {
  name: 'App',
  components: { 
    Block,
    Result
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {

    start() {
      this.delay = 2000 + Math.random() * 2000
      this.isPlaying = true;
      this.showResults = false
      // console.log(this.delay)
    },
    endGame(reaction) {
      this.score = reaction
      this.isPlaying = false
      this.showResults = true
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
