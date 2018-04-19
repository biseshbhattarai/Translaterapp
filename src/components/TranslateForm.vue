<template>
  <div id="translateform">
      <form v-on:submit="submitform">
          <input type="text" v-model="textToTranslate" placeholder="Enter a word">
          <input type="Submit" value="Translate">
      </form>
  </div>
</template>

<script>

export default {
  name: 'TranslateForm',
  data(){
      return {
          textToTranslate:''
      }
  },
  methods: {
      submitform(e){
          this.$emit('submitform', this.textToTranslate)
          e.preventDefault();
      }
  }
}
</script>

<style>

  
</style>
