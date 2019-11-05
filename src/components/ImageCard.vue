<template>
  <div class="image-card">
    <section :key="image.id">
      <h4>{{ image.copyright }}</h4>    
      <img :src="image.baseimageurl"/>
    </section>
  </div>
</template>




<script>
export default {
  name: 'image-card',
  props: {
    image: Object
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
img {
  height: 300px;
}
</style>