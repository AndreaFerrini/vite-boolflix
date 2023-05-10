<script>

import { store } from "../store"


export default {
    name: "HeaderComp",
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <header class="d-flex p-4 align-items-center justify-content-between">
        <h1>Boolflix</h1>
        <div>
            <input type="text" placeholder="search" v-model="store.testoRicerca">
            <button class="btn btn-outline-danger" @click="$emit('apiCall')">Start</button>
        </div>
    </header>
</template>

<style scoped>
header {
    background-color: rgb(0, 8, 29);
}

h1 {
    color: rgb(255, 0, 0);
    transform: rotateY(-30deg) rotateX(30deg);
    perspective: 800px;
    transform-origin: 50% 0;
    font-size: 55px;
}

button {
    color: rgb(255, 0, 0);
    border-color: rgb(255, 0, 0);
}

button:hover {
    border-color: rgb(255, 0, 0);
}
</style>
