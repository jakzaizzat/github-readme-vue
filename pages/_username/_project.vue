<template>
  <div>
    <vue-showdown :markdown="content" />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    try {
      let res = await $axios.$get(
        "/repos/" + params.username + "/" + params.project + "/readme"
      );
      return { content: atob(res.content) };
    } catch (e) {
      console.log(e);
      return e;
    }
  },
  data() {
    return {
      content: ""
    };
  }
};
</script>

<style lang="postcss">
h1 {
  @apply font-semibold text-lg;
}
h1,
h2,
h3,
h4,
h5,
ul,
p {
  @apply mb-2 leading-normal;
}
pre {
  @apply bg-gray-200 p-2 rounded mb-3 overflow-x-scroll;
}
ul {
  @apply list-disc;
}

table {
  @apply mb-8 border border-gray-200;
}
th,
td {
  @apply py-2 px-4 text-left;
}

th {
  @apply bg-gray-200;
}
</style>
