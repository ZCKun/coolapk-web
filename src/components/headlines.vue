<template>

  <div class="content">
    <h1> {{ msg }} </h1>
  </div>

</template>

<script>
import axios from "axios"
import md5 from "md5"

export default {
  name: "headlines",
  methods: {
    get_app_token: function () {
      let ts = new Date() / 1000 * 1000;
      let hex_t = ts.toString(16);
      let str = "token://com.coolapk.market/c67ef5943784d09750dcfbb31020f0ab?"
          + md5(hex_t)
          + "$8513efac-09ea-3709-b214-95b366f1a185&com.coolapk.market";
      return md5(btoa(str));
    }
  },
  mounted() {
    // let app_token = this.get_app_token();
    // this.msg = app_token;

    // axios.defaults.headers.get['X-App-Token'] = this.get_app_token();
    // instance.get("https://api.coolapk.com/v6/main/indexV8?page=1")
    axios.get("https://api.coindesk.com/v1/bpi/currentprice.json", { headers: {
        'X-App-Token': this.get_app_token()} })
        .then(response => (this.msg = response))
    // axios
    //     .get('/v6/main/indexV8?page=1')
    //     .then(response => (this.msg = response))
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>