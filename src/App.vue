<template>
  <div id="app">
    <inputForm />
  </div>
</template>

<script>
import inputForm from "./components/inputForm";

export default {
  name: "App",
  components: {
    inputForm,
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
