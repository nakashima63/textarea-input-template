<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <TextAreaWithTemplate />
</template>

<script>
import TextAreaWithTemplate from "./components/TextAreaWithTemplate.vue";
export default {
  name: "App",
  components: {
    TextAreaWithTemplate: TextAreaWithTemplate,
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
