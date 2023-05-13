<script>

export default {
    name: "SingleCard",
    props: ['infoFilm'],
    methods: {
        stampaBandiera() {
            if (this.infoFilm.original_language == 'en') {
                return '/public/images/en.png'
            } else if (this.infoFilm.original_language == 'i') {
                return '/public/images/it.png'
            } else if (this.infoFilm.original_language == 'es') {
                return '/public/images/es.png'
            } else if (this.infoFilm.original_language == 'fr') {
                return '/public/images/fr.png'
            } else if (this.infoFilm.original_language == 'jpn') {
                return '/public/images/jpn.png'
            } else {
                return '/'
            }
        }
    }
}

</script>

<template>
    <div class="col-3 p-3">
        <div class="card">
            <img src="#" class="card-img-top" :alt="infoFilm.original_title">
            <div class="card-body">
                <h5 class="card-title">{{ infoFilm.original_title }}</h5>
                <p class="card-text">{{ infoFilm.overview }}</p>
                <!-- <h6>{{ infoFilm.original_language }}</h6> -->
                <img :src="stampaBandiera()" width="50" alt="">
                <h6>{{ infoFilm.vote_average }}</h6>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
