<template>
    <ul class="list-unstyled">
        <li class="mb-2" v-for="movie in movies" :key = "movie.id">
            <div class="card text-center">
                <div class="card-body row">
                    <div class="col-8 d-flex justify-content-center flex-column">
                        <h4 class="card-title">{{ movie.name }}</h4>
                        <p class="card-subtitle mb-2 text-muted">
                            Added on {{ formatedDate(movie.date) }}
                        </p>
                    </div>
                    <div class="col col-4">
                        <a :href="movie.url" target="_blank" class="btn btn-outline-primary btn-md mb-2">View Movie</a>
                        <button @click="deleteMovie(movie.id)" class="btn btn-outline-danger btn-md">Delete</button>
                    </div>
                </div>
            </div>
        </li>
    </ul>
</template>

<script>
import moment from 'moment'
export default {
    name: "MovieList",
    props: ["movies", "deleteMovie"],    // [List, Method]
    methods: {
        formatedDate: function(date){
            return moment(date).format("DD/MM/YYYY [at] hh:mm a")
        }
    }
}
</script>

<style>

</style>