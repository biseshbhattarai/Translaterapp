<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered By Vue.js</h5>
    <TranslateForm v-on:submitform="translateText"/>
    <TranslateOutput v-text='translatedText'/>
    <div>
      <button v-on:click="buttonclick">Click me</button>
      <p v-if="show">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Incidunt voluptatum sequi iste rem, iusto eius eveniet debitis nam aut, ipsa deserunt molestiae vel beatae odit, quasi reprehenderit reiciendis dignissimos illo?</p>
    </div>

  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  components:{
    TranslateForm,
    TranslateOutput
    
  },
  data: function(){
    return {
      translatedText:'',
      show: true
    }
  },
  methods:{
    translateText:function(text){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180415T134832Z.b6d64d9a92a1e3e4.afa3ea50162b2c13794133b35de4b08bdcabce25&lang=ne&text='+text)
      .then((response) => {
        this.translatedText = response.body.text[0]
      });
    },
    buttonclick: function(){
      this.show = !show;

    }
  }

  
}
</script>


