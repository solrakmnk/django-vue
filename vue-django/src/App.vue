<template>
  <div id="app">
    <Home></Home>
    <Pixabay></Pixabay>
  </div>
</template>

<script>
import Home from "./components/Home"
import Pixabay from "./components/Pixabay/Pixabay";

export default {
  name: 'App',
  components: {
    Home,
    Pixabay,
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
