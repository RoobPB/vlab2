<script>


import { ref } from 'vue'

export default {
    setup() {
        const userName =  ref('')

        const submitForm = () => {
            console.log(userName.value)
        }
        return {
            userName,
            submitForm
        }
    }
}

</script>

<template>

<div class="SearchApp">

      <input class="form-control me-2" type="search" placeholder="Search" v-model="userName">
      <button @click="submitForm" class="btn btn-outline-success" type="submit">Search </button>
    </div>


</template>




<style>

.SearchApp {
    position: absolute;
    width: 389px;
    height: 48px;
    left: 40%;
    top: 90px;
    }


</style>
