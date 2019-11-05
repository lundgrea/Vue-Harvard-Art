<template>
  <div class="gallery-card">
    <section :key="gallery.id">
      <h4>{{ gallery.labeltext }}</h4>    
      <h5>{{ gallery.name }}</h5>    
      <h6>{{ gallery.theme }}</h6>    

    </section>
  </div>
</template>




<script>
export default {
  name: 'gallery-card',
  props: {
    gallery: Object
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