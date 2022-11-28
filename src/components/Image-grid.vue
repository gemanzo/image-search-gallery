<template>
  <div class="grid">
    <ImageCard
      v-for="image in images"
      :src="image.urls.regular"
      :alt="image.alt_description"
      :key="image.id"
    ></ImageCard>
  </div>
</template>

<script>
import ImageCard from './Image-card.vue';
export default {
  name: 'image-grid',
  props: { images: Array },
  data() {
    return {};
  },
  components: {
    ImageCard,
  },
};
</script>

<style scoped>
.grid {
  margin-top: 50px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  padding: 2rem;
}
</style>
