<template>
  <div>
    <div><h3>How fast can you catch me?</h3></div>
    <button @click="gamePlay" :disabled="isPlaying">Play</button>
    <div v-if="end">
      <ScoreResult :score="score" />
    </div>
    <div v-if="isPlaying">
      <ClickBlog :delay="delay" @endGame="endGame" />
    </div>
  </div>
</template>

<script>
import ClickBlog from "./components/ClickBlog.vue";
import ScoreResult from "./components/ScoreResult.vue";
export default {
  components: { ClickBlog, ScoreResult },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      end: false,
    };
  },
  methods: {
    gamePlay() {
      this.end = false;
      this.isPlaying = true;
      this.delay = 1000 + Math.random() * 5000;
      // console.log("app" + (1000 + Math.random() * 5000));
    },
    endGame(score) {
      this.score = score;
      this.isPlaying = false;
      this.end = true;
    },
  },
};
</script>

<style scoped>
h3 {
  color: green;
  text-align: center;
}

button {
  display: block;
  margin: auto;
  width: 150px;
  padding: 3px;
  background: rgb(4, 241, 4);
  border-radius: 5px;
  color: white;
  font-size: large;
  font-weight: 900;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  border-color: rgb(140, 115, 144);
  box-shadow: 20px;
}
</style>
