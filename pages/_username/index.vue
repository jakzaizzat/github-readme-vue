<template>
  <div>
    <h1 class="text-lg mb-4 font-semibold">List repo from {{username}}</h1>
    <div v-if="repos.length > 0" class="flex flex-wrap -mx-2">
      <div v-for="repo in repos" :key="repo.id" class="w-full md:w-1/3 px-2 mb-4">
        <Card :repo="repo" />
      </div>
    </div>
    <div v-else>No repo available</div>
  </div>
</template>

<script>
import Card from "@/components/Card";
export default {
  components: {
    Card
  },
  async asyncData({ $axios, params }) {
    try {
      let data = await $axios.$get("/users/" + params.username + "/repos");
      return { repos: data };
    } catch (e) {
      return { repos: [] };
    }
  },
  data() {
    return {
      repos: [],
      username: ""
    };
  },
  mounted() {
    this.username = this.$route.params.username;
  }
};
</script>
