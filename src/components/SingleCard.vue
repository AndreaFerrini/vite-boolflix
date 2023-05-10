<script>

export default {
    name: "SingleCard",
    props: ['infoFilm']
}

</script>

<template>
    <div class="col-3">
        <div class="card">
            <img src="#" class="card-img-top" :alt="infoFilm.original_title">
            <div class="card-body">
                <h5 class="card-title">{{ infoFilm.original_title }}</h5>
                <p class="card-text">{{ infoFilm.overview }}</p>
                <h6>{{ infoFilm.original_language }}</h6>
                <h6>{{ infoFilm.vote_average }}</h6>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
