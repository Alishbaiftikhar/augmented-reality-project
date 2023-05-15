<template>
  <div class="app">
    <ARModelViewer />
  </div>
</template>

<script>
import ARModelViewer from "./components/ARModelViewer.vue";

export default {
  name: "App",
  components: {
    ARModelViewer,
  },
};
</script>

<style>
.app {
  margin: 1em;
  padding: 0;
  font-family: Google Sans, Noto, Roboto, Helvetica Neue, sans-serif;
  color: #244376;
}
</style>
