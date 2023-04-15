<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <button @click="getCatFact" class="btn btn-outline-primary">
      Click me
    </button>
    <p>{{ fact }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    title: String,
  },
  data() {
    return { fact: "" };
  },
  methods: {
    async getCatFact() {
      var response = await fetch("https://catfact.ninja/fact");
      const data = await response.json();
      this.fact = data.fact;
    },
  },
};
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
