<template>
  <div class="color-card">
    <section v-for="color in colors" :key="color.id">
      <div class="color-card-hex" v-bind:style="{ backgroundColor: color.hex}"
      ></div>
      <h4>{{ color.name }}</h4>    

    </section>
  </div>
</template>




<script>
export default {
  name: 'color-card',
  props: {
    colors: Array
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
.color-card-hex {
  height: 100px;
  width: 100px;
  }
</style>