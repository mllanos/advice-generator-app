<template>
  <div class="advice">
    <div class="header">Advice #{{ id }}</div>
    <quote class="quote"> "{{ advice }}" </quote>
    <hr />
    <button class="circle-dice" @click="roll">
      <font-awesome-icon :icon="['fas', 'dice-five']" size="lg" />
    </button>
  </div>
</template>

<script>
export default {
  name: "AdviceContainer",
  data() {
    return {
      id: null,
      advice: null,
    };
  },
  mounted() {
    this.roll();
  },
  methods: {
    async getAdvice() {
      const response = await fetch('https://api.adviceslip.com/advice');
      const data = await response.json();
      return data.slip;
    },
    async roll() {
      const { id, advice } = await this.getAdvice();
      this.id = id;
      this.advice = advice;
    },
  },
};
</script>

<style scoped>
.advice {
  background: red;
  color: #fff;
  margin: 25%;
  min-height: 50px;
  min-width: 50px;
  padding: 25px;
  border-radius: 0.5em;
  text-align: center;
  font-weight: bold;
}
.header {
}
.quote {
  font-size: 1.5em;
}

.circle-dice {
  border-radius: 50%;
  background: green;
  width: 50px;
  height: 50px;
  font-size: 1.5em;
  font-weight: bold;
  color: #000;
  text-align: center;
  line-height: 50px;
  cursor: pointer;
  border: none;
}
</style>
