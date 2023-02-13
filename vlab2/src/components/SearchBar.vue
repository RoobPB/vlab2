<script>

import bild from '/Users/RobEr/vlab2/vlab2/public/bild.json'


export default {
    props: {
        showSearch: { // Ändra namn
            type: Boolean, // Ändra namn
            default: false // Ändra namn
        }

    },

  data() {
    return {
      bild,
      searchTerm: '',
      filteredData: [],
      filteredList: [],
      msg: 'Sök på en årstid eller klicka på knappen', // Det är denna som skriver ut texten
    }
  },
  methods: {
    search() {
      this.filteredData = this.bild.filter(item => {
        return item.category.toLowerCase().includes(this.searchTerm.toLowerCase());  /*||
               item.description.toLowerCase().includes(this.searchTerm.toLowerCase()); */
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
    <div class="card" v-for="item in filteredData" :key="item.id">
        <img :src="item.image" alt="Bild bild"> <!-- Har försökt få bilden att visas när man går in på sidan (när bilden är en empty
        string kommer alla bilder visas annars inte) -->
        <h2>{{ item.name }}</h2>
        <p>{{ item.description }}</p>


    </div>

</div>

  <!-- Detta var ett test för att få ut texten <h1 class="SearchInfo" v-for="item in filteredData" :key="item.id">
        {{ item.name }} {{ item.category }}</h1> -->

<!--<h2>{{ msg || 'No props passed yet' }}</h2> -->
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
    color: rgb(31, 136, 5); /* Färgen på bildnamn */
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
