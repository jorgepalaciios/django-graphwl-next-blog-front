<script setup>
import PostList from "../components/PostList.vue"

const { result, loading, error } = {
  error: {message: "no connection to the GRaphQL API yet!"},
}
</script>

<template>
  <h2>Recent Posts</h2>
  <div v-if="loading">Loading</div>
  <div v-if="error" class="warn"></div>
  <PostList v-else :post="result.allPosts"/>
</template>

<style scoped>
  h2 {
    color: blue;
  }
</style>