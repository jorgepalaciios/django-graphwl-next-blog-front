<script setup>
import PostList from "../components/PostList.vue"

const { result, loading, error } = {
  error: { meesage: "No connection to the GraphQL API yet!"},
}
</script>

<template>
  <div v-if="loading">Loading...</div>
  <div v-else-if="error"> {{ error.meesage }}</div>
  <section v-else :set="author = result.authorByUserName">
    <h2>{{ author.user.username }}</h2>
    <template v-if="author.username.firstName && author.user.lastName">
      <h3>{{ author.user.firstName }} {{ author.user.lastName }}</h3>
    </template>
    <p v-if="author.bio">
      {{ author.bio }}
      <template v-if="author.website">
        Learn more aboyt {{ author.user.username }} on their
        <a :href="author.website">webiste</a>
      </template>
    </p>
    <h3>Posts</h3>
    <PostList 
      v-if="author.PostSet"
      :posts="author.PostSet"
      :showAuthor="false"
    />
    <p v-else> the author hasn't posted yet °-°</p>
  </section>
</template>

<style scoped>
  h2 {
    color: red;
  }
</style>