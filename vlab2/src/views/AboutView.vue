<script setup>
    import SearchBar from '../components/SearchBar.vue'
    import BildDs from '../components/BildDs.vue'
    import axios from 'axios'
</script>

<template>
  <div class="about">
    <p>Massa about text om sidan ...................Lorem ipsum dolor sit amet,
    consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
    dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
    ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
     dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat
     nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
      culpa qui officia deserunt mollit anim id est laborum. </p>
  </div>
  <div class="about">
    <h1>Samtliga bilder i projektet (mountade) </h1>
  </div>
  <div id="sortering">
        <div class="container text-center">
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
            //    msg: 'Kategori',  Ta bort denna + classen title
                spas: [], //Ändra namn
                bildInfo: 'bild.json',
                showSearch: false,

            }
        },
        components: { 'bild-ds': BildDs, SearchBar },

       mounted() {
            this.getBild()
        },

        methods: {
            async getBild() {
                try {
                    const response = await axios.get(this.bildInfo)
                    this.spas = (response.data)
                    console.log(response.data)
                }
                catch (error) {
                    console.log(error)
                }
            }
        }
    }
</script>

<style>
#sortering {
        display: flex;
        justify-content: center;
        margin-top: 10vh;
        margin-bottom: 10vh;
    }
  .about {
    min-height: 10vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white
  }

</style>
