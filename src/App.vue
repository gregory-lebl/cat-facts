<template>
  <h1>{{ fact }}</h1>
  <li v-for="fact in facts" :key="fact.id">
    <Fact :fact="fact.text"/>
  </li>
</template>

<script>
import Fact from './components/Fact.vue'
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      facts: ''
    }
  },
  components: {
    Fact
  },
 mounted(){
   axios
    .get('https://cat-fact.herokuapp.com/facts')
    .then(response => this.facts = response.data)
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
</style>
