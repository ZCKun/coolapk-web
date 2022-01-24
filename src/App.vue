<template>
  <div id="app">
    <tail></tail>
    <headlines msg="123"></headlines>
  </div>
</template>

<script>
import tail from "./components/tail.vue"
import headlines from "./components/headlines.vue"

export default {
  name: 'App',
  components: {
    tail,
    headlines
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
