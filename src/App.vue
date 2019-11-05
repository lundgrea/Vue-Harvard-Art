<template>
  <div id="app">
    <img alt="Harvard Art Mueseum logo" src="./assets/HAM-logo-reduced.png">
    <h1>HAM Art Randomizer</h1>

    <h2>Randomized Audio</h2>
    <audio-card :audio="audio" />

    <h2>Randomized Video</h2>
    <video-card :video="video" />

    <h2>Randomized Color</h2>
    <color-card :color="color" />

    <h2>Randomized Culture</h2>
    <culture-card :culture="culture" />

    <h2>Randomized Exhibition</h2>
    <exhibition-card :exhibition="exhibition" />

    <h2>Randomized Gallery</h2>
    <gallery-card :gallery="gallery" />

    <h2>Randomized Image</h2>
    <image-card :image="image" />

    <h2>Randomized Object</h2>
    <object-card :object="object" />

    <h2>Randomized Period</h2>
    <period-card :period="period" />

    <h2>Randomized Publication</h2>
    <publication-card :publication="publication" />

    <h2>Randomized Technique</h2>
    <technique-card :technique="technique" />

  </div>
</template>

<script>
import VideoCard from './components/VideoCard.vue'
import AudioCard from './components/AudioCard.vue'
import ColorCard from './components/ColorCard.vue'

//could do 
//culture - https://api.harvardartmuseums.org/culture?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//exhibition - https://api.harvardartmuseums.org/exhibition?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//gallery - https://api.harvardartmuseums.org/gallery?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//image - https://api.harvardartmuseums.org/image?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//object - https://api.harvardartmuseums.org/object?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//period - https://api.harvardartmuseums.org/period?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//publication - https://api.harvardartmuseums.org/publication?apikey=8520a750-fe96-11e9-9058-a9d79115374a
//technique - https://api.harvardartmuseums.org/technique?apikey=8520a750-fe96-11e9-9058-a9d79115374a


export default {
  name: 'app',
  components: {
    VideoCard,
    AudioCard,
    ColorCard
  },
  data() {
    return {
      videos: [],
      video: {},
      audios: [],
      audio: {},
      colors: [],
      color: {},
      isLoading: true,
      error: ''
    }
  },
  mounted: function() {
    this.getVideos() 
    this.getAudios()
    this.getColors()
  },
  methods: {
    generateRandom: function () {
      return Math.round(Math.random() * 10)
    },
    getVideos: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch('https://api.harvardartmuseums.org/video?apikey=8520a750-fe96-11e9-9058-a9d79115374a')
        const data = await response.json()
        this.videos = data.records
        this.video = this.videos[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getAudios: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch('https://api.harvardartmuseums.org/audio?apikey=8520a750-fe96-11e9-9058-a9d79115374a')
        const data = await response.json()
        this.audios = data.records
        this.audio = this.audios[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getColors: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch('https://api.harvardartmuseums.org/color?apikey=8520a750-fe96-11e9-9058-a9d79115374a')
        const data = await response.json()
        this.colors = data.records
        this.color = this.colors[index]
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
