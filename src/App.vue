<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>Blog 🐻</h1>

      <nav>
        <RouterLink to="/">Posts</RouterLink>
        <RouterLink :to="{name: 'author'}">Author</RouterLink>
        <RouterLink :to="{name: 'post'}">Post</RouterLink>
        <RouterLink :to="{name: 'tag'}">Tag</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>


<style scoped>
  h1 {
    text-align: center;
    font-weight: bold;
    margin-bottom: 1rem;
  }

  header {
    border-bottom: 1px solid #ccc;
    margin-bottom: 1rem;
  }

  nav {
    text-align: center;
    margin: 1rem 0;
  }

  nav a {
    padding: 0.5rem;
  }

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }


  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
