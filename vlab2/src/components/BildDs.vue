<template>
    <div class="col">
        <div class="card" style="width: 16rem">
            <img v-bind:src="offer.image" class="card-img-top" alt="bild">
            <!-- offer.image här har gjort bilden lägger sig i rutan efter loopen -->

            <div class="card-body">
            <h2>{{ offer.name}}</h2> <!-- Skriver ut name i ett p -->
                <p class="card-text">
                    {{ offer.description }} <!-- Skriver ut description i ett p -->
                </p>

            </div>
        </div>
    </div>

</template>

<script>
    export default {
        mounted() {
            console.log('Komponent mountad!')
        },
        data() {
            return {

        }
    },
        props: {
            offer: {
                required: true,
                type: Object
            }
        }
    }

</script>

<style>




</style>
