<template>
    <div class="col">
        <div class="card" style="width: 18rem">
            <img src="../assets/img/andy-holmes-LUpDjlJv4_c-unsplash.jpg" class="card-img-top" alt="...">

            <div class="card-body">
                <p class="card-text">
                    Some quick example text to build on the card title and make
                    up the bulk of the card's content.
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
                bilder: [
                    '../assets/img/andy-holmes-LUpDjlJv4_c-unsplash.jpg',
                    '../assets/img/annie-spratt-wuc-KEIBrdE-unsplash.jpg',
                    '../assets/img/tony-lee-8IKf54pc3qk-unsplash.jpg',
                    '../assets/img/tony-lee-8IKf54pc3qk-unsplash.jpg'
                ]
            }
        }
    }
</script>

<style>



</style>
