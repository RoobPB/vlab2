<script>

import SearchBar from './SearchBar.vue';

export default {
    components: {
        SearchBar
    },
    data(){
        return {
            greeting: '',

        }
    }
    }





</script>
<template>
    <SearchBar :search='greeting'/>
    <div id="bild">
        <img
            src="../assets/img/andy-holmes-LUpDjlJv4_c-unsplash.jpg"
            class="img-fluid"
            alt="bild :D"
        /> 
        <div class="MainSearch">


        </div>

    </div>
    <div id="searchText"></div>



</template>













<style scoped>
    #bild img {
        margin: 0 auto;
        height: auto;
        overflow-x: hidden;
        position: absolute;
        width: 1950px;

    }

    .MainSearch {
        position: absolute;
        top: 5%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
        height: 30px;
    }



    #searchText {
        position:relative;
        left: 50%;
        color: rgb(199, 36, 36);
        height: 30px;
    }
</style>
