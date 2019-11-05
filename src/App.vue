<template>
  <div id="app">
    <img alt="Harvard Art Mueseum logo" src="./assets/HAM Logo.png">
    <Video msg="Welcome to Your Daily Harvard Art Museum"/>
  </div>
</template>

<script>
import Video from './components/Video.vue'

export default {
  name: 'app',
  components: {
    Video
  },
  data() {
    return {
      video: [],
      isLoading: true,
      error: ''
    }
  },
  mounted: function() {
    this.getVideos() 
  },
  methods: {
    getVideos: async function() {
      try { 
        const response = await fetch('https://api.harvardartmuseums.org/video?apikey=8520a750-fe96-11e9-9058-a9d79115374a')
        const data = await response.json()
        console.log(data.records)
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
