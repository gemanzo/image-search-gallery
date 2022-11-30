<template>
  <div class="grid">
    <div class="container" v-for="image in images">
      <ImageCard
        :image="image"
        :src="image.urls.regular"
        :alt="image.alt_description"
        :key="image.id"
      ></ImageCard>
      <p v-if="isSelected" class="author">
        {{ image.user.first_name }} {{ image.user.last_name }}
      </p>
    </div>
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
  width: 80vw;
  height: 100vh;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-gap: 0.5rem;
  margin: auto;
  margin-top: 5rem;
  padding: 2rem;
}

.author {
  color: white;
  position: relative;
  top: -15px;
  left: 0px;
  font-size: x-small;
  padding-bottom: 5px;
  margin-left: 5px;
}
</style>
