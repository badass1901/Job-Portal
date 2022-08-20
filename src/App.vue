<template>

  <div class="container">
    <NavigationBar />


    <router-view />
  </div>
</template>

<script>
import NavigationBar from "./components/NavigationBar.vue";
export default {
  data() {
    return {};
  },

  components: { NavigationBar }
};
</script>

<style>
</style>
