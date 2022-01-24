<template>

  <div class="main">
    <h1>hello world</h1>
    <h2>{{ info }}</h2>
  </div>

</template>

<script>
import axios from 'axios'

export default {
  name: "home",
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (info = response ))
  }
}
</script>

<style scoped>

</style>