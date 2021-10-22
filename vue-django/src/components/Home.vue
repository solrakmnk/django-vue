<template>
  <b-container>
    <b-row>
      <b-col>
        <h1>Welcome <small>by Carlos</small></h1>
      </b-col>
    </b-row>
    <b-row>
      <b-col v-for="red in redes" :key="red.red">
      <b-link :href="red.url" target="_blank">{{red.red}}</b-link>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>

export default {
  name: 'Home',
  data() {
    return {
      redes: [
        {
          red: "Twitter",
          url: "http://twitter.com/solrakmnk"
        }
      ]
    }
  }
}
</script>
<style>

</style>