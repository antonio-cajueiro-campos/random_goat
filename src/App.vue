<template>
  <div id="app">
    <input type="submit" @click="getGoat()">
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return { goat: [] };
  },
  methods: {
    randomize() {
      
    },
    getGoat() {
      const proxyurl = "https://cors-anywhere.herokuapp.com/";
      const url = `https://placegoat.com/200/200`
      fetch(proxyurl + url)
      .then(response => response.json())
      .then(contents => console.log(contents))
      .catch(() => console.log("Can’t access " + url + " response. Blocked by browser?"))
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
