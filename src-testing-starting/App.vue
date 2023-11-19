<template>
  <div>
    <h1>Hello Vue</h1>
    <div v-if="showModal">
      <ModalBox
        :TitleText="TitleText"
        :DataText="dataText"
        :Theme="theme"
        @close="showModal = false"
      >
        <template v-slot:links>
          <a href="#">Sing In</a>
          <a href="#">Log Out</a>
        </template>
      </ModalBox>
    </div>
    <button @click="showModal = !showModal">Open Modal</button>
    <button @click="showModal = !shohwModal">Logout</button>
  </div>
</template>
<script>
import ModalBox from "@/components/ModalBox.vue";
export default {
  components: { ModalBox },
  name: "App",
  data() {
    return {
      TitleText: "Welcome My App",
      dataText: "Welcome Developer Thetzinsoe",
      theme: "success",
      showModal: false,
    };
  },
};
</script>
<style scoped>
h1 {
  /* background: gray; */
  color: rgb(3, 69, 34);
  font-style: normal;
  text-align: center;
}
button {
  background-color: green;
  padding: 5px;
  border-radius: 10px;
  color: white;
  /* box-shadow: 5px; */
}
</style>
