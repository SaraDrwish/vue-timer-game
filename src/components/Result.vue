<template>
  <div class="Results">
    <p  >reaction time is : {{ score }}  ms </p>
    <p class="rank"> {{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  
   data() {
    return {
 
      rank: null,
 
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "woooooooooooow so faast yooo "
    } else if(this.score < 400){
      this.rank = "ummmmmmmmmmm  "
    } else {
      this.rank = "slowwwww ...... "
    }

  }

}
</script>

<style>

.rank{
  color: mediumturquoise;
  font-size: 22px;
}

</style>


