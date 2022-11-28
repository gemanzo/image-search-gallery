<template>
  <div
    class="search-box"
    :class="this.images.length > 1 ? 'default-position' : ''"
  >
    <button class="btn-search">
      <i class="fas fa-search"></i>
    </button>
    <input
      @keypress.enter="getImages"
      @blur="this.error = false"
      v-model="query"
      type="text"
      class="input-search"
      placeholder="Press Enter to Search..."
    />
  </div>
  <div class="error-msg" v-if="error">Please type something</div>

  <image-grid :images="images" v-if="showGrid"> </image-grid>
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
      error: false,
      showGrid: false,
    };
  },

  methods: {
    async getImages() {
      if (this.query.length < 1) {
        this.error = true;
      } else this.error = false;
      const res = await axios.get(
        `https://api.unsplash.com/search/photos?query=${this.query}&client_id=${process.env.VUE_APP_PROJECT_ACCESS_KEY}`
      );
      this.images = res.data.results;
      this.query = '';
      console.log(this.images);
      this.showGrid = true;
    },
  },
  components: {
    ImageGrid,
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
  display: flex;
  justify-content: center;
  align-items: center;
}
.search-box {
  width: fit-content;
  height: fit-content;
  position: relative;
  top: 400px;
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

.error-msg {
  position: relative;
  font-size: 20px;
  font-weight: lighter;
  color: red;
  text-align: center;
  margin-top: 10px;
  top: 400px;
}
.default-position {
  position: relative;
  top: 10px;
  margin: auto;
}
</style>
