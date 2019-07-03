<template>
  <nuxt-link
    :to="{ name: 'username-project', params: { username: username, project: repo.name  }}"
    class="card"
  >
    <div>
      <h3>{{repo.name}}</h3>
    </div>
  </nuxt-link>
</template>


<script>
export default {
  props: {
    repo: {
      required: true
    }
  },
  data() {
    return {
      username: ""
    };
  },
  methods: {
    openRepo(name) {
      this.$router.push({
        name: "username-project",
        params: {
          username: this.$route.params.username,
          project: name
        }
      });
    }
  },
  created() {
    this.username = this.$route.params.username;
  }
};
</script>

<style lang="postcss" scoped>
.card {
  @apply rounded bg-gray-200 block overflow-hidden shadow cursor-pointer h-full;
}
.card:hover {
  @apply bg-red-100;
}
.card div {
  @apply px-6 py-4;
}
.card h3 {
  @apply font-medium text-lg text-gray-900;
}
</style>
