<template>
  <FiftyFestival />
</template>

<script>
import FiftyFestival from "./components/FiftyFestival.vue";

export default {
  name: "App",
  components: {
    FiftyFestival,
  },
};
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
