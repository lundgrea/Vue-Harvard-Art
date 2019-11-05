<template>
  <div class="audio-card">
    <section v-for="audio in audios" :key="audio.id">
      <h4>{{ audio.description }}</h4>
      <a :href="audio.primaryurl">Listen</a>
      <a :href="audio.transcripturl">Read</a>
    </section>
  </div>
</template>

<script>
export default {
  name: 'audio-card',
  props: {
    audios: Array
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