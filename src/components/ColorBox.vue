<template>
  <div class="color-box" :style="{ 'background-color': color }">
    Component Content: {{ color.toUpperCase() }}
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: "purple",
    },
  },
};
</script>

<style>
.color-box {
  text-align: center;
  padding: 25px;
  font-size: 1.5rem;
  color: white;
  user-select: none;
}

.is-unique {
  box-sizing: border-box;
  gap: 10px;
  margin-top: 50px;
  padding: 20px;
  width: 90%;
}
</style>