<template>
  <div class="api">
    <h1>This is an api page</h1>
    <h2>info</h2>
     {{ info }}
  </div>
</template>

<script>
import axios from "axios";

export default {
  data(){
    return{
      info: [],
    }
  },
  mounted(){
    axios
      .get("http://127.0.0.1:8000/api/jobs/1/")
      // .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => {
        this.info = response;
        console.log("取得成功", response);
      })
    },
  }

</script>
