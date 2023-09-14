<template>
  <main class="container"><HomePage /></main>
</template>

<script lang="ts">
import HomePage from "./components/HomePage.vue";
export default {
  components: {
    HomePage,
  },
  setup() {
    return {};
  },
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  margin: 0 auto;
}
</style>
