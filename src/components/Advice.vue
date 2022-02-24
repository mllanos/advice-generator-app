<template>
  <div class="advice">
    <div class="header">ADVICE #{{ id }}</div>
    <quote class="quote">“{{ advice }}”</quote>
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
      const response = await fetch("https://api.adviceslip.com/advice");
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
  background: hsl(217, 19%, 24%);
  color: #ffff;
  margin: 25%;
  min-height: 50px;
  min-width: 50px;
  padding: 35px;
  border-radius: 0.5em;
  text-align: center;
  font-weight: bold;
}
.header {
  padding-bottom: 10px;
  color: hsl(150, 100%, 66%);
  letter-spacing: 4px;
  font-size: 12px;
}
.quote {
  font-size: 28px;
}

hr {
  border: 0;
  height: 1px;
  background: hsl(217, 19%, 38%);
  margin: 25px 0px;
  text-align: center;
  line-height: 1px;
  height: 1px;
  font-size: 1em;
  border-style: solid;
  border-color: #676767;
  margin: 20px 10px;
  overflow: visible;
}
hr:after {
  content: "||";
  background-color: #303b49;
  padding: 0 0.5em;
}

.circle-dice {
  border-radius: 50%;
  background: hsl(150, 100%, 66%);
  width: 50px;
  height: 50px;
  font-size: 18px;
  font-weight: bold;
  color: #000;
  text-align: center;
  line-height: 50px;
  cursor: pointer;
  border: none;
}
</style>
