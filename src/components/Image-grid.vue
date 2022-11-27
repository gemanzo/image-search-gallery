<template>
  <div>
    <img
      v-for="image in images"
      :src="baseUrl + image.id"
      :alt="image.alt_description"
    />
  </div>
</template>

<script>
export default {
  name: 'image-grid',
  props: { images: Array },
  data() {
    return {
      baseUrl: 'https://api.unsplash.com/photos/',
    };
  },
};
</script>

<style scoped></style>
