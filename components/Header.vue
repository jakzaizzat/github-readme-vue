<template>
  <div class="bg-red-100">
    <div class="container py-0">
      <nuxt-link :to="{ name: 'index'  }">Home</nuxt-link>
    </div>
  </div>
</template>

<style lang="postcss" scoped>
.container {
  @apply py-3 font-semibold;
}
</style>
