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
  padding: 0px 10px;
  margin: 0 auto;
}
</style>
