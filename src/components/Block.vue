<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
     click
  </div>
</template>

<script>

export default {

  props: ["delay"],
  data() {
    return {
      showBlock: false,
      time: null,
      reaction:0
  }  
  },
  mounted() {
    console.log("mounted");
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
      // console.log(this.delay)
    } , this.delay )
  },
  // updated() {
  //   console.log("updated")
  // },
  // unmounted() {
  //   console.log("unmounted")
  // },
  methods: {
    startTimer() {
      this.time=
        setInterval(()=> {
        this.reaction += 10
      } , 10 )
    },
    stopTimer() {
      clearInterval(this.time)
      // console.log(this.reaction)
      this.$emit('end', this.reaction)
    }
  }


}

</script>


<style>

.block{
  width: 33rem;
  border-radius: 3rem;
  background-color: slategray;
  color: lightcoral;
  text-align: center;
  padding: 4%;
  margin:2% auto;
}

</style>