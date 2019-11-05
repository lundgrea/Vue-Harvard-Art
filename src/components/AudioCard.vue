<template>
  <div class="audio-card">
    <section :key="audio.id">
      <h4>{{ audio.description }}</h4>    
      <ul>
      <li><a :href="audio.primaryurl">Listen</a></li>
      <li><a v-if="audio.transcripturl !== null" :href="audio.transcripturl">Read</a></li>
      </ul>
    </section>
  </div>
</template>




<script>
export default {
  name: 'audio-card',
  props: {
    audio: Object
  },
  methods: {

  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>