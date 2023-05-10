<script>

import {store} from "../store"


export default{
    name: "HeaderComp",
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <header class="d-flex  p-4 align-items-center justify-content-between">
        <h1>Boolflix</h1>
        <form class="d-flex">
            <input type="text" placeholder="search" v-model="store.testoRicerca">
            <button @click="$emit('apiCall')">Start</button>
        </form>
    </header>
</template>

<style scoped>

header{
    background-color: rgb(0,8,29);
}

h1{
    color: red;
    transform: rotateY(-30deg) rotateX(30deg);
    perspective: 800px;
    transform-origin: 50% 0;
    font-size: 55px;
}


</style>
