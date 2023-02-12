<script setup>
    import BildImage from '../components/BildImage.vue'
    import SearchBar from '../components/SearchBar.vue'
    import BildDs from '../components/BildDs.vue'
    import axios from 'axios'
</script>

<template>
    <div class="message">
    <h1>{{ msg }}</h1></div>
    <BildImage />
    <SearchBar />






    <div id="sortering">
        <div class="container text-center">
            <SearchBar :show-search="showSearch" @toggleVisibility="toggleVisibility" /> <!-- togglevis är ny funkar ej -->
            <button class="btn btn-warning" @click="showSearch = !showSearch">Show searchbar</button> <!-- Detta är toggle knappen -->
            <div class="row align-items-center">
                <!-- Loopar bild i bilder och lagt till ett key som kommer binda den första bilen med id i json -->
                <!-- offer här binds till spa  Bör byta namn här :) -->
                <BildDs v-for="spa in spas" :key="spa.id" :offer="spa" /> <!-- Ändra namn -->
            </div>
        </div>
    </div>
</template>

<script>
    export default {

        data() {
            return {

                showSearch: false,
                showSearchBar: false

            }
        },
        methods: {
            toggleVisibility() {
                this.showSearch = !this.showSearch // Ny
            }
        }



    }
</script>

<style scoped>




.btn-warning{
    color: black;
    font-weight:bold;

    display: flex;
        justify-content: center;
        left: 1%;
        top: -120px;


}


</style>
