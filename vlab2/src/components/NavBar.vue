<script setup>
    import { RouterLink, RouterView } from 'vue-router'
</script>
<template>
    <nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand">Bilder</a>
    <form class="d-flex" role="search">
      <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success" type="submit">Search</button>
    </form>
  </div>
</nav>
    <RouterView />
</template>
<style scoped>

    .navbar-brand {
        color: white;
        font-size: 10vh;
    }
    .btn btn-outline-success {
        background-color: rgb(248, 98, 90);
    }
</style>
