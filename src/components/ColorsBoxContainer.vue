<template>
  <div class="btns-container">
    <ColorBox v-for="(color, index) in colors" :key="index" :color="color" />
  </div>
</template>

<script>
import ColorBox from "./ColorBox.vue";
import ColorsMock from "@/mocks/ColorsMock.js";
export default {
  components: {
    ColorBox,
  },
  data() {
    return {
      colors: ColorsMock,
    };
  },
};
</script>

<style>
.btns-container {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  gap: 10px;
  margin-top: 50px;
  padding: 20px;
  border: 1px solid #ddd;
  width: 90%;
}
</style>