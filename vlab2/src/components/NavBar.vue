<script setup>
    import { RouterLink, RouterView } from 'vue-router'
</script>
<template>
   <nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <RouterLink class="navbar-brand" to="/">Home</RouterLink>
    <RouterLink class="nav-link active" aria-current="page" to="/about">About</RouterLink>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">


    </div>
  </div>
</nav>
    <RouterView />
</template>
<style scoped>

    .navbar-brand {
        color: white;
        font-size: 10vh;
        left: 50%;
        top: 90%;
    }
    .navbar-brand:hover{
        color: rgb(97, 97, 105);

    }

    .aboutl, h1{
        position:sticky;
        width: 239px;
        height: 48px;
        left: 85%;
        top: 50%;
        font-size: 10vh;
        color: white;
    }
    .nav-link{
        position: absolute;
        color:white;
        font-size: 10vh;
        left: 85%;
    }
    .nav-link:hover{
        color: rgb(97, 97, 105);
    }

</style>
