<template>
  <VueNavbar />
  <VuePhotos />
  <VueComments />
  <VueFetch />
</template>

<script>
import VueComments from "./components/VueComments.vue";
import VueFetch from "./components/VueFetch.vue";
import VuePhotos from "./components/VuePhotos.vue";
import VueNavbar from "./components/VueNavbar.vue";

export default {
  name: "App",
  components: {
    VueNavbar,
    VuePhotos,
    VueComments,
    VueFetch,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
