<template>
  <div class="publication-card">
    <section :key="publication.id">
      <h4>{{ publication.title }}</h4>  
      <h5>{{ publication.volumenumber }}</h5>  
      <h6>{{ publication.volumetitle }}</h6>  
      <p>{{ publication.publicationdate }}</p>    
      <p>{{ publication.format }}</p>    
    </section>
  </div>
</template>




<script>
export default {
  name: 'publication-card',
  props: {
    publication: Object
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