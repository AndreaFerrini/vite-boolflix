<script>

import axios from "axios";
import { store } from "./store";
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
  },
  data() {
    return {
      store
    }
  },
  methods: {
    searchFilm() {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.apiKey}&query=${store.testoRicerca}`)
        .then((res) => {
          console.log(res.data.results)
          store.arrayFilm = res.data.results
        })
    }
  }
}

</script>

<template>
  <HeaderComp @apiCall="searchFilm()" />
  <MainComp />
</template>

<style></style>
