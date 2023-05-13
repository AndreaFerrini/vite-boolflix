<script>

export default {
    name: "SingleCard",
    props: ['info'],
    methods: {
        stampaBandiera() {
            if (this.info.original_language == 'en') {
                return '/images/en.png'
            } else if (this.info.original_language == 'it') {
                return '/images/it.png'
            } else if (this.info.original_language == 'es') {
                return '/images/es.png'
            } else if (this.info.original_language == 'fr') {
                return '/images/fr.png'
            } else if (this.info.original_language == 'ja') {
                return '/images/jpn.png'
            } else {
                return '/'
            }
        },
        getTitle() {
            if (this.info.original_title) {
                return this.info.original_title
            } else {
                return this.info.original_name
            }
        },
        getImages() {
            if (this.info.poster_path) {
                return `https://image.tmdb.org/t/p/w342/${this.info.poster_path}`
            } else if (this.info.poster_path == null) {
                return `/images/image-not-available.jpg`
            }
        },
        getVote() {
            return Math.ceil(this.info.vote_average / 2)
        }
    }
}

</script>

<template>
    <div class="col-3 p-3">
        <div class="card">
            <img :src="getImages()" class="card-img-top" :alt="getTitle()">
            <div class="card-body">
                <h5 class="card-title">{{ getTitle() }}</h5>
                <p class="card-text">{{ info.overview }}</p>
                <!-- <h6>{{ info.original_language }}</h6> -->
                <img :src="stampaBandiera()" width="50" alt="">
                <h6>Voto: {{ getVote() }}</h6>
                <div>
                    <i v-for="n in 5" class="fa-star" :class="(n <= getVote()) ? 'fa-solid' : 'fa-regular'"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
