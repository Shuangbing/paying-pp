<template>
  <div class="app" id="app">
    <Main />
  </div>
</template>

<script>
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main
  }
};
</script>

<style>
.app {
  margin: 0;
  padding: 0;
}
</style>