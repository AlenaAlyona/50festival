<template>
  <FiftyFestival />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import FiftyFestival from "./components/FiftyFestival.vue";

export default defineComponent({
  name: "App",
  components: {
    FiftyFestival,
  },
});
</script>

<style>
#app {
  font-family: "LunchType-Regular", sans-serif;
  font-size: 18px;
  line-height: 1.5;
}
</style>
