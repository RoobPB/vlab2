<script setup>
    import BildImage from '../components/BildImage.vue'
    import SearchBar from '../components/SearchBar.vue'
    import BildDs from '../components/BildDs.vue'
    import axios from 'axios'
</script>

<template>
    <BildImage />
    <SearchBar />

    <div id="sortering">
        <div class="container text-center">
            <SearchBar :show-search="showSearch" />
            <button
                class="btn btn-warning"
                v-if="!showSearch"
                @click="showSearch = !showSearch"
            >
                Show searchbar
            </button>


            <div class="row align-items-center"></div>
        </div>
    </div>
</template>

<script>
    export default {
        components: {
            SearchBar
        },

        data() {
            return {
                showSearch: false
                /* Sätts denna till true kommer den gula -
                Show searchbar inte visas och istället visa search */
            }
        }
    }
</script>

<style scoped>
    .btn-warning {
        color: black;
        font-weight: bold;

        display: flex;
        justify-content: center;
        left: 1%;
        top: -120px;
    }
</style>
