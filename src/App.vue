<template>
  <div>
    <Header />
    <RouterView />
  </div>
</template>
<script>
import Header from "./Layout/Header.vue";
export default {
  components: {
    Header,
  },
};
</script>
