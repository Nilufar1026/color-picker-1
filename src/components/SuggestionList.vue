<template>
  <ul>
    <li 
      v-for="color in matchingColors" 
      :key="color"
      @click="$emit('click', color)"
    >{{color}}</li>
  </ul>
</template>

<script>
export default {
  props: ['match'],
  computed:{
    
    color(){return this.$store.state.colors},
    matchingColors(){
      return this.$store.getters.matchingColors(this.match)
    }
  
  },
  // data(){ return {
  //   colors: ['red','green','blue'] // Change this to a vuex getter that filters based on this.match
  // }},
}
</script>

<style scoped>
ul{
  position: absolute;
}
</style>>

