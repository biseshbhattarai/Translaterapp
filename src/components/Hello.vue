<template>
<div>
  <h1>Welcome to my App</h1>
  <button v-on:click="hitball"><img src="../assets/logo.png"></button>
   <p>The button above has been clicked {{ counter }} times.</p>
</div>
</template>


<script>
export default {
  name:'Hello',
  data: function(){
      return {
          counter: 0
      }
  },
  methods : {
      hitball: function(){
          console.log(this.counter+=1)
      }
  }
}
</script>
