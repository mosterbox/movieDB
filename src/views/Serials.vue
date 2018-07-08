<template>
  <div class="serials">
    <MovieItem v-for="movieItem in movieList"
      :posterPath="movieItem.poster"
      :title="movieItem.title"
      :key="movieItem.id"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import MovieItem from '@/components/MovieItem.vue'

import axios from 'axios'

const URL = 'https://api.themoviedb.org/3/tv/popular';
const URL_IMG = 'https://image.tmdb.org/t/p/w185';
const API = 'api_key=ceec93d778f59df4556ed45a60299413';

export default {
    name: 'Films',
    components: {
      MovieItem
    },

    data() {
        return {
            result: [],
            movieList: []
        }
    },
    
    created() {
        axios.get(`${ URL }?${ API }`)
        .then(response => {
            this.result = response.data.results;
            this.movieList = this.result.map(
                function(movieItem) {
                  let newMovieList = {};
                    newMovieList.poster = `${ URL_IMG }${ movieItem.poster_path }`;
                    newMovieList.title = movieItem.name;
                    return newMovieList;
                }
            )
        })
        .catch(e => {
            console.log(e);
        })
    }    
}
</script>

<style lang="scss">
  .serials{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    align-content: center;
  }
</style>
