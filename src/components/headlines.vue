<template>

  <div class="content">
    <h1> {{ msg }} </h1>
  </div>

</template>

<script>
export default {
  name: "headlines",
  mounted() {
    this.msg = "1231"
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>