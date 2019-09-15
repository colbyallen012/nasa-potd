<template>
  <div id="app">
    <Header/>
    <Potd v-bind:photo='photo'/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Potd from './components/Potd.vue'

export default {
  name: 'app',
  components: {
    Header,
    Potd
  },
    data() {
    return {
      photo: {}
    } 
  },
  created: function() {
    this.fetchData();
  },
  methods: {
    fetchData: async function() {
      try {
        const result = await fetch(`https://api.nasa.gov/planetary/apod?api_key=${process.env.VUE_APP_API_KEY}`)
        const photo = await result.json()
        this.photo = photo
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
