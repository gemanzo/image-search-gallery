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

html {
  margin: 0px;
  padding: 0px;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(238, 174, 202, 0.2);
  background: radial-gradient(
    circle,
    rgba(238, 174, 202, 0.2) 0%,
    rgba(148, 187, 233, 0.2) 0%
  );
  font-family: 'Dosis', sans-serif;
  font-weight: 300;
}
</style>
