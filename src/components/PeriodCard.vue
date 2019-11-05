<template>
  <div class="period-card">
    <section :key="period.id">
      <h4>{{ period.name }}</h4>    
    </section>
  </div>
</template>




<script>
export default {
  name: 'period-card',
  props: {
    period: Object
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