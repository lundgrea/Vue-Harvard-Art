<template>
  <div class="video-card">
    <section :key="video.id">
      <h4>{{ video.description }}</h4>
      <p>{{ video.primaryurl}}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'video-card',
  props: {
    video: Object
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