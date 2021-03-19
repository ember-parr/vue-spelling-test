<template>
  <div id="app">
    <h1>Spelling Test</h1>
    <spelling-test />
  </div>
</template>

<script>
import SpellingTest from './components/SpellingTest.vue';
export default {
  name: "App",
  components: {
    SpellingTest,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
