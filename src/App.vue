<template>
  <div id="app">
    <img alt="Harvard Art Mueseum logo" src="./assets/HAM-logo-reduced.png">
    <h1>Daily Audio & Video Exhibit</h1>
    <h2>Today's Audio</h2>
    <audio-card :audios="audios" />

    <h2>Today's Video</h2>
    <video-card :videos="videos" />

  </div>
</template>

<script>
import VideoCard from './components/VideoCard.vue'
import AudioCard from './components/AudioCard.vue'

export default {
  name: 'app',
  components: {
    VideoCard,
    AudioCard
  },
  data() {
    return {
      videos: [],
      audios: [],
      isLoading: true,
      error: ''
    }
  },
  mounted: function() {
    this.getVideos() 
    this.getAudios()
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
    },
    getAudios: async function() {
      try { 
        const response = await fetch('https://api.harvardartmuseums.org/audio?apikey=8520a750-fe96-11e9-9058-a9d79115374a')
        const data = await response.json()
        this.audios = data.records
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
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
