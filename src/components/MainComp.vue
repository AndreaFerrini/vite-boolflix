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
        <div class="container d-flex justify-content-around flex-wrap">
            <SingleCard v-for="(elem, index) in store.arrayFilm" :key="index" :infoFilm="elem" />
        </div>
    </main>
</template>

<style scoped>
main {
    background-color: rgb(0, 8, 29);
}
</style>
