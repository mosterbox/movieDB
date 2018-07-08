<template>
    <div class="movie_list">
        <h1>It's MovieItem</h1>
        <MovieItem />
    </div>
</template>

<script>

import MovieItem from '@/components/MovieItem.vue'

export default {
    props: {
        posterSrc: String
    },
    
    name: 'movi_list',
    components: {
        MovieItem
  }
}
</script>
