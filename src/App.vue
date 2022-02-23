<template>
  <Advice id="1" />
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
.attribution {
  font-size: 11px;
  text-align: center;
}

.attribution a {
  color: hsl(228, 45%, 44%);
}
</style>
