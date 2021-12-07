<template>
  <div
    class="btn"
    :style="{ 'background-color': buttonColor }"
    @click="setSelectedButtonBox()"
  >
    Show Component {{ buttonColor.toUpperCase() }}
  </div>
</template>

<script>
export default {
  props: {
    buttonColor: {
      type: String,
      default: "purple",
    },
  },
  methods: {
    setSelectedButtonBox() {
      this.$emit("ButtonBoxHasClicked", this.buttonColor);
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