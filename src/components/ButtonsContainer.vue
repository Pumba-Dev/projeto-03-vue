<template>
  <div class="buttons-container">
    <ButtonBox
      v-for="(color, index) in colors"
      :key="index"
      :buttonBoxColor="color"
      @ButtonBoxHasClicked="setSelectedButtonBox($event)"
    />
  </div>
</template>

<script>
import ButtonBox from "@/components/ButtonBox.vue";
import ColorsMock from "@/mocks/ColorsMock.js";
export default {
  components: {
    ButtonBox,
  },
  data() {
    return {
      colors: ColorsMock,
    };
  },
  methods: {
    setSelectedButtonBox(ButtonBoxColor) {
      // console.log(ButtonBoxColor);
      this.$emit("ButtonBoxHasClicked", ButtonBoxColor);
    },
  },
};
</script>

<style scoped>
.buttons-container {
  display: flex;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  gap: 20px;
  border: 1px solid #ddd;
  padding: 20px;
  box-shadow: 0px 2px rgba(0, 0, 0, 0.1);
  width: max-content;
}
</style>