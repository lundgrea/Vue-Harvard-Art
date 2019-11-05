<template>
  <div id="app">
    <img alt="Harvard Art Mueseum logo" src="./assets/HAM-logo-reduced.png">
    <h1>HAM Art Randomizer</h1>
    <p>{{ this.date }}</p>

    <div class="card">
      <h2>Audio</h2>
      <audio-card :audio="audio" />
    </div>

    <div class="card">
    <h2>Video</h2>
    <video-card :video="video" />
    </div>

    <div class="card">
      <h2>Color</h2>
      <color-card :color="color" />
    </div>

    <div class="card">
      <h2>Image</h2>
      <image-card :image="image" />
    </div>

    <div class="card">
      <h2>Culture</h2>
      <culture-card :culture="culture" />
    </div>

    <div class="card">
      <h2>Exhibition</h2>
      <exhibition-card :exhibition="exhibition" />
    </div>

    <div class="card">
      <h2>Gallery</h2>
      <gallery-card :gallery="gallery" />
    </div>

    <div class="card">
      <h2>Object</h2>
      <object-card :object="object" />
    </div>

    <div class="card">
      <h2>Period</h2>
      <period-card :period="period" />
    </div>

    <div class="card">
      <h2>Publication</h2>
      <publication-card :publication="publication" />
    </div>

    <div class="card">
    <h2>Technique</h2>
    <technique-card :technique="technique" />    
    </div>


  </div>
</template>

<script>
import VideoCard from './components/VideoCard.vue'
import AudioCard from './components/AudioCard.vue'
import ColorCard from './components/ColorCard.vue'
import CultureCard from './components/CultureCard.vue'
import ExhibitionCard from './components/ExhibitionCard.vue'
import GalleryCard from './components/GalleryCard.vue'
import ImageCard from './components/ImageCard.vue'
import ObjectCard from './components/ObjectCard.vue'
import PeriodCard from './components/PeriodCard.vue'
import PublicationCard from './components/PublicationCard.vue'
import TechniqueCard from './components/TechniqueCard.vue'


export default {
  name: 'app',
  components: {
    VideoCard,
    AudioCard,
    ColorCard,
    CultureCard,
    ExhibitionCard,
    GalleryCard,
    ImageCard,
    ObjectCard,
    PeriodCard,
    PublicationCard,
    TechniqueCard
  },
  data() {
    return {
      video: {},
      audio: {},
      color: {},
      culture: {},
      exhibition: {},
      gallery: {},
      image: {},
      object: {},
      period: {},
      publication: {},
      technique: {},
      isLoading: true,
      error: '',
      key: process.env.VUE_APP_KEY, 
      date: ''
    }
  },
  mounted: function() {
    this.getVideos() 
    this.getAudios()
    this.getColors()
    this.getCultures()
    this.getExhibitions()
    this.getGalleries()
    this.getImages()
    this.getObjects()
    this.getPeriods()
    this.getPublications()
    this.getTechniques()
    this.displayDate()
  },
  methods: {
    displayDate() {
    let today = new Date().toLocaleDateString();
    this.date = today
    },
    generateRandom: function () {
      return Math.round(Math.random() * 10)
    },
    getVideos: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/video?${this.key}`)
        const data = await response.json()
        const videos = data.records
        this.video = videos[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getAudios: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/audio?${this.key}`)
        const data = await response.json()
        const audios = data.records
        this.audio = audios[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getColors: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/color?${this.key}`)
        const data = await response.json()
        const colors = data.records
        this.color = colors[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getCultures: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/culture?${this.key}`)
        const data = await response.json()
        const cultures = data.records
        this.culture = cultures[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
     getExhibitions: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/exhibition?${this.key}`)
        const data = await response.json()
        const exhibitions = data.records
        this.exhibition = exhibitions[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getGalleries: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/gallery?${this.key}`)
        const data = await response.json()
        const galleries = data.records
        this.gallery = galleries[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
      getImages: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/image?${this.key}`)
        const data = await response.json()
        const images = data.records
        this.image = images[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getObjects: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/object?${this.key}`)
        const data = await response.json()
        const objects = data.records
        this.object = objects[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getPeriods: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/period?${this.key}`)
        const data = await response.json()
        const periods = data.records
        this.period = periods[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getPublications: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/publication?${this.key}`)
        const data = await response.json()
        const publications = data.records
        this.publication = publications[index]
      } catch (errorMsg) {
        this.error = errorMsg
      }
    },
    getTechniques: async function() {
      let index = this.generateRandom()
      try { 
        const response = await fetch(`https://api.harvardartmuseums.org/technique?${this.key}`)
        const data = await response.json()
        const techniques = data.records
        this.technique = techniques[index]
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
.card {
  border: 2px solid black;
  width: 60%;
  margin: auto;
}
</style>
