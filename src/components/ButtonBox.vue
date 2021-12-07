<template>
  <div
    class="btn"
    :style="{ 'background-color': buttonBoxColor }"
    @click="setSelectedButtonBox()"
  >
    Show Component {{ buttonBoxColor.toUpperCase() }}
  </div>
</template>

<script>
export default {
  props: {
    buttonBoxColor: {
      type: String,
      default: "purple",
    },
  },
  methods: {
    setSelectedButtonBox() {
      this.$emit("ButtonBoxHasClicked", this.buttonBoxColor);
    },
  },
};
</script>

<style scoped>
.btn {
  max-width: max-content;
  max-height: max-content;
  color: white;
  padding: 10px;
  user-select: none;
}
</style>