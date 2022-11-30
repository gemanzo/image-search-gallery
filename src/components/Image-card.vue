<template>
  <img
    :class="isSelected ? 'selected' : ''"
    @click="isSelected = !isSelected"
  />
</template>

<script>
export default {
  name: 'Image-card',
  data() {
    return { isSelected: false };
  },
  props: {
    image: Object,
  },
};
</script>

<style scoped>
.image-container {
  width: 200px;
  height: auto;
}
img {
  object-fit: cover;
  max-width: 100%;
  height: 100%;
  border-radius: 2%;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px,
    rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px,
    rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
  cursor: pointer;
}

.selected {
  position: fixed;
  width: 50%;
  height: 70%;
  margin: auto;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

@media screen and (max-width: 878px) {
  .selected {
    height: 40%;
    width: 90%;
  }
}
</style>
