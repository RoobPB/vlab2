<script>




export default {
    data() {
        return {
        s: [],
        bildInfo: 'bild.json',
        search: ''
    }
},
methods: {
    n(){
        return this.s
    }
},


}



</script>

<template>

<div class="SearchApp">
  <input btntext class="form-control me-2" type="search" placeholder="Search" v-model="search">
  <button @click="getBild" class="btn btn-outline-success" type="submit">Search</button>
</div>
<!--<h2>{{ msg || 'No props passed yet' }}</h2> -->








</template>




<style>

.SearchApp {
    position: absolute;
    width: 389px;
    height: 48px;
    left: 40%;
    top: 90px;
    }

    h2 {
        color: white;
}
</style>
