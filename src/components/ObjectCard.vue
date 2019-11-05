<template>
  <div class="object-card">
    <section :key="object.id">
      <h4>Century: {{ object.century }}</h4>    
      <h5>Classification: {{ object.classification }}</h5>    
      <h6>Culture: {{ object.culture }}</h6>   
      <p>Dated: {{ object.dated }}</p> 
      <p>Department: {{ object.department }}</p> 

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