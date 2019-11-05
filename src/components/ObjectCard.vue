<template>
  <div class="object-card">
    <section :key="object.id">
      <h4>{{ object.description }}</h4>    
    </section>
  </div>
</template>




<script>
export default {
  name: 'object-card',
  props: {
    object: Object
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