<template>
  <div class="view-p">
    <div class="main-container">
      <ButtonsContainer
        @ButtonBoxHasClicked="setSelectedButtonBoxColor($event)"
      />
      <component
        :is="ButtonBoxColorHasSelected"
        :color="selectedButtonBoxColor"
        :class="['is-unique']"
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
    ButtonsContainer,
    ColorsBoxContainer,
  },
  data() {
    return {
      selectedButtonBoxColor: "",
      InitialColorBox: "ColorsBoxContainer",
    };
  },
  computed: {
    ButtonBoxColorHasSelected() {
      return this.selectedButtonBoxColor == ""
        ? this.InitialColorBox
        : ColorBox;
    },
  },
  methods: {
    setSelectedButtonBoxColor(ButtonBoxColor) {
      // console.log(ButtonBoxColor);
      this.selectedButtonBoxColor = ButtonBoxColor;
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