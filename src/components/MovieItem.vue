<template lang="html">
    <div class="movie_item">
        <div class="movie_img">
            <img :src="posterPath" :alt="title">
        </div>
        <h3>{{ title }}</h3>
    </div>
</template>

<script>

export default {
  name: 'MovieItem',
  props: ['title', 'posterPath']
}

</script>