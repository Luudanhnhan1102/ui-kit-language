<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <uikit-language></uikit-language>
  </div>
</template>

<script>
import UikitLanguage from "./components/Language.vue";

export default {
  name: "App",
  components: {
    "uikit-language": UikitLanguage,
  },
  data() {
    return {};
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
