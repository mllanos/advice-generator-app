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
  font-family: 'Manrope';
  font-weight: 800;
}
html {
   margin: 0px;
   height: 100%;
   width: 100%;
}

body {
   margin: 0px;
   min-height: 100%;
   width: 100%;
}
</style>
