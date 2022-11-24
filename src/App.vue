<template>
  <h1 id="title">Search for the best <span id="keyword">pictures</span></h1>
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
  background: rgba(238, 174, 202, 0.2);
  background: radial-gradient(
    circle,
    rgba(238, 174, 202, 0.2) 0%,
    rgba(148, 187, 233, 0.2) 0%
  );
  font-family: 'Dosis', sans-serif;
  font-weight: 300;
}
#title {
  text-transform: uppercase;
  text-align: center;
  margin-top: 2rem;
}
#keyword {
  background: #ff0000;
  background: linear-gradient(
    to right,
    #ff0000 0%,
    #ffff00 25%,
    #05c1ff 50%,
    #ffff00 75%,
    #ff0000 100%
  );
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 2rem;
  transition: font-size, 0.5s;
}

#keyword:hover {
  font-size: 2.2rem;
}
</style>
