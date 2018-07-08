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
  props: {
      title: String,
      posterPath: String
  }
}

</script>

<style lang="scss">
    .movie_item {
        display: flex;
        flex-direction: column;
        max-width: 25%;
    }
</style>
