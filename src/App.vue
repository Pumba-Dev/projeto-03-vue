<template>
  <div class="view-p">
    <div class="main-container">
      <ButtonsContainer @ButtonBoxHasClicked="onButtonBoxHasClicked($event)" />
      <component
        :is="currentUseColorBox"
        :color="selectedButtonBox"
        :class="['unique']"
      />
    </div>
  </div>
</template>

<script>
import ButtonsContainer from "@/components/ButtonsContainer.vue";
import ColorsBoxContainer from "./components/ColorsBoxContainer.vue";
import ColorBox from "@/components/ColorBox.vue";
export default {
  components: {
    ColorsBoxContainer,
    ButtonsContainer,
  },
  data() {
    return {
      selectedButtonBox: "",
      currentUseColorBox: "ColorsBoxContainer",
    };
  },
  methods: {
    onButtonBoxHasClicked(ButtonBoxColor) {
      console.log(ButtonBoxColor);
      this.selectedButtonBox = ButtonBoxColor;
      this.currentUseColorBox = ColorBox;
    },
  },
};
</script>

<style scoped>
.view-p {
  display: flex;
  justify-content: center;
}

.main-container {
  font-family: "Montserrat";
  width: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>