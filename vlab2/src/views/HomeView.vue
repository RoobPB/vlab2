<script setup>
    import BildImage from '../components/BildImage.vue'
    import SearchBar from '../components/SearchBar.vue'
    import BildDs from '../components/BildDs.vue'
</script>

<template>
    <BildImage />
    <SearchBar />
    <h1 class="title">{{ message }}</h1>
    <div id="sortering">
    <div class="container text-center">
        <div class="row align-items-center">
            <BildDs />
            <BildDs />
            <BildDs />
            <BildDs />
        </div>
    </div>
</div>
</template>

<script>
    export default {
        data() {
            return {
                message: 'Kategori'
            }
        }
    }
</script>

<style scoped>
    #sortering{
        display:flex;
        justify-content: center;
        margin-top: 10vh;
        margin-bottom: 10vh;

    }


    .title, h1 {
        color: aliceblue;
        display: flex;
        justify-content: center;
        margin-top: 2vh;
    }
</style>
