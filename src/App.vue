<template>
  <Advice />
  <Attribution />
</template>

<script>
import Advice from "./components/Advice.vue";
import Attribution from "./components/Attribution.vue";

export default {
  name: "App",
  components: {
    Advice,
    Attribution,
  },
};
</script>

<style>
body {
  background: #212632;
}
</style>
