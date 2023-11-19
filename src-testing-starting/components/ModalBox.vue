<template>
  <div class="backdrop" @click.self="closeModal()">
    <div
      class="modalBox"
      :class="{ success: Theme == 'success', danger: Theme == 'delete' }"
    >
      <!-- <h1>{{ TitleText }}</h1>
      <p>{{ DataText }}</p> -->
      <slot>Default</slot>
      <slot name="links"></slot>
    </div>
    <!-- <h4>hello</h4> -->
  </div>
</template>

<script>
export default {
  name: "ModalBox",
  props: ["TitleText", "DataText", "Theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
template {
  padding: 0;
  margin: 0;
}
.backdrop {
  background: rgb(0, 0, 0, 0.3);
  height: 100%;
  width: 100%;
  position: fixed;
  top: 0;
}
.modalBox {
  background: rgb(255, 255, 255);
  /* display: inline-block; */
  width: 400px;
  padding: 20px;
  margin: 150px auto;
  border-radius: 10px;
}
h4 {
  background: blue;
}
.success {
  color: white;
  background: green;
}
.danger {
  color: white;
  background: crimson;
}
</style>
