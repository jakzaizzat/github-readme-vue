<template>
  <form @submit.prevent="submit" class="relative flex items-center mb-8">
    <input
      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
      v-model="username"
      placeholder="Enter github username"
    />
    <button type="submit">
      <svg
        class="ml-4 bg-red-500 rounded p-2 h-10 w-12 fill-current text-white"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        width="24"
        height="24"
      >
        <path
          class="heroicon-ui"
          d="M16.32 14.9l5.39 5.4a1 1 0 0 1-1.42 1.4l-5.38-5.38a8 8 0 1 1 1.41-1.41zM10 16a6 6 0 1 0 0-12 6 6 0 0 0 0 12z"
        />
      </svg>
    </button>
  </form>
</template>


<script>
export default {
  props: {
    value: {
      required: true
    }
  },
  data() {
    return {
      username: "",
      repos: []
    };
  },
  methods: {
    submit() {
      this.$router.push({
        name: "username",
        params: { username: this.username }
      });
    }
  }
};
</script>
