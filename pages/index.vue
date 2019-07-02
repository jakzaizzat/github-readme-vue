<template>
  <div>
    <SearchBar v-model="result" />
  </div>
</template>

<script>
import SearchBar from "@/components/SearchBar";
export default {
  components: { SearchBar },
  data() {
    return {
      result: ""
    };
  }
};
</script>