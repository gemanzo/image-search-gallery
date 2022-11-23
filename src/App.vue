<template>
  <Searchbar text="Search an image"></Searchbar>
</template>

<script>
import Searchbar from './components/Search-bar.vue';
export default {
  data() {
    return {};
  },
  methods: {},
  components: { Searchbar },
};
</script>

<style>
*,
*::after,
*::before {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
