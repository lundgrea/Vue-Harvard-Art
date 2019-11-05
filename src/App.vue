<template>
  <div id="app">
    <img alt="Harvard Art Mueseum logo" src="./assets/HAM Logo.png">
    <h1>Welcome to Your Daily Harvard Video Art Museum</h1>
    <video-card :videos="videos" />
  </div>
</template>

<script>
import VideoCard from './components/VideoCard.vue'

export default {
  name: 'app',
  components: {
    VideoCard
  },
  data() {
    return {
      videos: [],
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
        this.videos = data.records
      } catch (errorMsg) {
        this.error = errorMsg
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
