<template>
  <div class="blog" v-if="showBlog" @click="stopTimer">
    <p>Click Me Quick!</p>
  </div>
</template>

<script>
export default {
  name: "ClickBlog",
  props: ["delay"],
  data() {
    return {
      showBlog: false,
      score: 0,
      timer: null,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlog = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.score += 50;
        console.log(this.score);
      }, 50);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("endGame", this.score);
      //   console.log("score is : " + this.score);
    },
  },
};
</script>

<style scoped>
.blog {
  background: aqua;
  width: 300px;
  height: 200px;
  margin: 50px auto;
  border-radius: 10px;
}
p {
  text-align: center;
  padding-block-start: 90px;
}
</style>
