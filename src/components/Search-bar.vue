<template>
  <div id="input-container">
    <input
      type="text"
      required
      name="input"
      id="input-query"
      placeholder="text"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    text: String,
  },
  methods: {},
};
</script>

<style scoped>
* {
  display: flex;
  justify-content: center;
  margin: 2rem;
  padding: 0.6rem;
}
#input-query {
  width: 50vw;
  text-align: center;
  margin: auto;
}
#input-query:focus {
  outline: none;
}
#input-query:focus::placeholder {
  color: transparent;
}
#input-cointainer {
  display: flex;
  justify-content: center;
  border: 1px solid #000;
  margin: auto;
}
</style>
