<script>

import { store } from "../store"
import SingleCard from "./SingleCard.vue"

export default {
    name: "MainComp",
    data() {
        return {
            store
        }
    },
    components: {
        SingleCard,
    }
}

</script>

<template>
    <main>
        <div class="container d-flex justify-content-around flex-wrap pb-5" v-if="store.arrayFilm.length" :key="index"
            :infoFilm="elem">
            <h3>Ecco i risultati dei film trovati:</h3>
            <div class="container d-flex justify-content-around flex-wrap pb-5">
                <SingleCard v-for="(film, index) in store.arrayFilm" :key="index" :info="film" />
            </div>
        </div>
        <div class="container d-flex justify-content-around flex-wrap pb-5" v-if="store.arraySerie.length">
            <h3>Ecco i risultati delle serie tv trovate:</h3>
            <div class="container d-flex justify-content-around flex-wrap pb-5">
                <SingleCard v-for="(serie, index) in store.arraySerie" :key="index" :info="serie" />
            </div>
        </div>
    </main>
</template>

<style scoped>
main {
    background-color: rgb(0, 8, 29);
}

h3 {
    color: white;
    display: block;
}
</style>
