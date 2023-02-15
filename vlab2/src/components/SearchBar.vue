<script>

import bild from '/Users/RobEr/vlab2/vlab2/public/bild.json'


export default {
    props: {
        showSearch: {
            type: Boolean,
            default: false
        }

    },

  data() {
    return {
      bild,
      searchTerm: '',
      fData: [],
      msg: 'Sök på en årstid eller klicka på knappen',
    }
  },
  methods: {
    search() {
      this.fData = this.bild.filter(item => {
        return item.category.toLowerCase().includes(this.searchTerm.toLowerCase()); /* Små eller stora bokstäver spelar ingen roll  */
      })
    }
  }
}
</script>

<template>

<div class="SearchApp" v-if="showSearch">
  <input btntext class="form-control me-2" type="search" placeholder="Search" v-model="searchTerm">
  <button @click="search" class="btn btn-outline-success" type="submit">Search</button>
  <p>{{ msg }}</p> <!-- Det är denna som skriver ut texten -->
</div>


<div class="card-container">
    <div class="card" v-for="item in fData" :key="item.id">
        <img :src="item.image" alt="Bild bild">
        <h2>{{ item.name }}</h2>
        <p>{{ item.description }}</p>


    </div>

</div>



</template>




<style>

.SearchApp {
    position: absolute;
    width: 400px;
    height: 48px;
    left: 40%;
    top: 90px;
    }
.SearchApp p{
    color: white;
    font-weight:bold;
    font-size:large;
    display: flex;
    justify-content: center;


}

h2 {
    color: rgb(31, 136, 5);
}
.btn{
position: relative;
color: white;
left: 101%;
top: -80%;
}

.SearchInfo {
    color: aqua;

}


.search-container {
  padding: 20px;
}

.card-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 40px;
  justify-content: center;
}

.card {
  width: 300px;
  height: 400px;
  overflow: hidden;
}

.card img {
    width: 100%;
    height: 68%;
    object-fit: cover;
}
.btn-outline-success {
  display: flex;

}


</style>
