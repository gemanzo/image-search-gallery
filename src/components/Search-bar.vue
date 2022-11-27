<template>
  <div class="search-box">
    <button @click="showquery" class="btn-search">
      <i class="fas fa-search"></i>
    </button>
    <input
      @keypress.enter="getImages"
      v-model="query"
      type="text"
      class="input-search"
      placeholder="Type to Search..."
    />
  </div>
  <image-grid> </image-grid>
</template>

<script>
import axios from 'axios';
import ImageGrid from './Image-grid.vue';

export default {
  name: 'SearchBar',
  data() {
    return {
      query: '',
      images: [],
    };
  },
  props: {
    text: String,
  },
  methods: {
    showquery() {
      console.log(this.query);
    },

    async getImages() {
      const res = await axios.get(
        `https://api.unsplash.com/search/photos?query=${this.query}&client_id=${process.env.VUE_APP_PROJECT_ACCESS_KEY}`
      );
      this.images = res.data.results;
      console.log(this.images);
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
body {
  margin: 0px;
  padding: 0px;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #130f40;
}
.search-box {
  width: fit-content;
  height: fit-content;
  position: relative;
}
.input-search {
  height: 50px;
  width: 50px;
  border-style: none;
  padding: 10px;
  font-size: 18px;
  letter-spacing: 2px;
  outline: none;
  border-radius: 25px;
  transition: all 0.5s ease-in-out;
  background-color: #22a6b3;
  padding-right: 40px;
  color: #fff;
}
.input-search::placeholder {
  color: rgba(255, 255, 255, 0.5);
  font-size: 18px;
  letter-spacing: 2px;
  font-weight: 100;
}
.btn-search {
  width: 50px;
  height: 50px;
  border-style: none;
  font-size: 20px;
  font-weight: bold;
  outline: none;
  cursor: pointer;
  border-radius: 50%;
  position: absolute;
  right: 0px;
  color: #ffffff;
  background-color: transparent;
  pointer-events: painted;
}
.btn-search:focus ~ .input-search {
  width: 300px;
  border-radius: 0px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.5);
  transition: all 500ms cubic-bezier(0, 0.11, 0.35, 2);
}
.input-search:focus {
  width: 300px;
  border-radius: 0px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.5);
  transition: all 500ms cubic-bezier(0, 0.11, 0.35, 2);
}
</style>
