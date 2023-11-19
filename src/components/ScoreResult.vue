<template>
  <div class="resultText">
    <h4>Your Score : {{ score }} ms</h4>
    <div v-if="score < 250">Your are too fast!</div>
    <div v-else-if="score > 250 && score < 500">Your are normal!</div>
    <div v-else>Your are too slow , Try again!</div>
  </div>
</template>

<script>
export default {
  name: "ScoreResult",
  props: ["score"],
  data() {
    return {};
  },
};
</script>

<style scoped>
h4 {
  text-align: center;
}
.resultText {
  text-align: center;
  margin: 20px auto;
  background: rgb(243, 243, 128);
  width: 250px;
  height: 140px;
  border-radius: 10px;
  padding-block-start: 20px;
  color: rgb(124, 3, 3);
}
</style>
