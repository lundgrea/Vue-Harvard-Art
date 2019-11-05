<template>
  <div class="video-card">
    <section v-for="video in videos" :key="video.id">
      <h2>{{ video.description }}</h2>
      <p>{{ video.primaryurl}}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'video-card',
  props: {
    msg: String,
    videos: Array
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