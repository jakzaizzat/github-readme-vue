<template>
  <div>
    <Header />
    <div class="container">
      <nuxt />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header";
export default {
  components: {
    Header
  }
};
</script>


<style lang="postcss">
.container {
  @apply max-w-3xl mx-auto py-16;
}
</style>
