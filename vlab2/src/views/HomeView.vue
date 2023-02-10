<script setup>
    import BildImage from '../components/BildImage.vue'
    import SearchBar from '../components/SearchBar.vue'
    import BildDs from '../components/BildDs.vue'
</script>

<template>
    <BildImage />
    <SearchBar />
    <h1 class="title">{{ msg }}</h1>
    <div id="sortering">
        <div class="container text-center">
            <div class="row align-items-center">



                <!-- Loopar bild i bilder och lagt till ett key som kommer binda den första bilen med id i json -->
                <!-- offer här binds till spa  Bör byta namn här :) -->
                <bild-ds v-for="spa in spas" :key="spa.id" :offer="spa" />
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                msg: 'Kategori',
                spas: [],
                bildInfo: 'bild.json'
            }
        },
        components: { 'bild-ds': BildDs },

        mounted() {
            this.getBild()
        },
        methods: {
            async getBild() {
                const response = await fetch(this.bildInfo)
                const data = await response.json()
                this.spas = data
                console.log(data)
            }
        }
    }
</script>

<style scoped>
    #sortering {
        display: flex;
        justify-content: center;
        margin-top: 10vh;
        margin-bottom: 10vh;
    }

.title,
    h1 {
        position: relative;
        color: aliceblue;
        display: flex;
        justify-content: center;
        margin-top: 2vh;
    }
</style>
