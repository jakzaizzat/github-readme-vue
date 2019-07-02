<template>
  <nuxt-link
    :to="{ name: 'username-project', params: { username: username, project: repo.name  }}"
    class="rounded bg-gray-200 block overflow-hidden shadow cursor-pointer h-full hover:bg-red-100"
  >
    <div class="px-6 py-4">
      <div class="font-medium text-lg text-gray-900">{{repo.name}}</div>
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
