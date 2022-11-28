<template>
  <img
    :images="images"
    @click="this.isOpen ? (this.isOpen = false) : (this.isOpen = true)"
    :class="isOpen ? 'open' : ''"
  />
</template>

<script>
export default {
  name: 'Image-card',
  data() {
    return { isOpen: false };
  },
  props: { images: Array },
};
</script>

<style scoped>
img {
  width: 18%;
  min-height: 300px;
  height: auto;
  transition: all 0.3s ease-in-out;
}
img:hover {
  transform: scale(1.2);
  box-shadow: 0px 15px 10px rgba(0, 0, 0, 0.95);
  border-radius: 1%;
  cursor: pointer;
}
.open {
  z-index: 9999;
  width: 75%;
  height: auto;
  position: absolute;
}
</style>
