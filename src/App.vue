<template>
  <div id="app">
    <Header/>
    <Potd v-bind:photo='photo' v-on:home-photo="homePhoto"/>
    <h2>Photos This Month</h2>
    <MonthPhotoContainer v-bind:monthPhotos='monthPhotos' v-on:view-photo="viewPhoto"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Potd from './components/Potd.vue'
import MonthPhotoContainer from './components/MonthPhotoContainer.vue'

export default {
  name: 'app',
  components: {
    Header,
    Potd,
    MonthPhotoContainer
  },
    data() {
    return {
      photo: {},
      monthPhotos: [],
      error: undefined,
      monthError: undefined,
      monthStart: undefined,
      today: undefined
    } 
  },
  created: function() {
    this.endDate();
    this.startDate();
    this.fetchData();
    this.fetchMonthData();
  },
  methods: {
    fetchData: async function() {
      try {
        const result = await fetch(`https://api.nasa.gov/planetary/apod?api_key=${process.env.VUE_APP_API_KEY}`)
        const photo = await result.json()
        this.photo = photo
      } catch (error) {
        this.error = error
      }
    },
    fetchMonthData: async function() {
      try {
        const result = await fetch(`https://api.nasa.gov/planetary/apod?api_key=${process.env.VUE_APP_API_KEY}&start_date=${this.monthStart}&end_date=${this.today}`)
        const monthPhoto = await result.json()
        this.monthPhotos = monthPhoto
      } catch (error) {
        this.monthError = error
      }
    },
      endDate: function() {
      var today = new Date();
      var dd = String(today.getDate()).padStart(2, '0');
      var mm = String(today.getMonth() + 1).padStart(2, '0'); 
      var yyyy = today.getFullYear();
      this.today = yyyy + '-' + mm + '-' + dd;
    },
    startDate: function() {
      var today = new Date();
      var mm = String(today.getMonth() + 1).padStart(2, '0'); 
      var yyyy = today.getFullYear();
      this.monthStart = yyyy + '-' + mm + '-' + '01';
    },
    viewPhoto(date) {
      let dated = this.monthPhotos.find(photo => {
        return photo.date === date
      })
      this.photo = dated
    },
    homePhoto() {
      let todaysDate = this.today
      let today = this.monthPhotos.find(photo => {
        return photo.date === todaysDate
      })
      this.photo = today
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #65727F;
  background-color: black;
}

h2 {
  color: orange;
  margin-top: 5px;
  margin-bottom: 0;
}
</style>

<style>

html {
  background-color: black;
}
</style>
