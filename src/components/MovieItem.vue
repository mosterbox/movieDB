<template lang="html">
    <div class="movie_item">
        <div class="movie_img">
            <img :src="posterPath">
            <h3 class="img_title">{{ title }}</h3>
        </div>
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
        justify-content: flex-end;
    }
    .movie_img {
        
    }
</style>
