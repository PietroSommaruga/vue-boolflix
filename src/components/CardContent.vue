<template>
    <div class="card">
      <div class="back-card py-4 px-3">
        <h3>{{card.title}}</h3>
        <h6> {{card.original_title}}</h6>

        <div class="language">
          <img v-if="languages.includes(card.original_language)" :src="require('@/assets/' + card.original_language + '.png')" alt=""/>  <!-- fixed -->
          <span v-else>Original language: {{ card.original_language }}</span>
        </div>

        <p>Voto: {{card.vote_average}}</p>
        <span> {{card.overview}}</span>
      </div>
      <a href="#">
        <img v-if="card.poster_path !== null" :src="`https://www.themoviedb.org/t/p/original${card.poster_path}`" alt="" />
        <img v-else src="@/assets/not-found.png" alt="" />
      </a>
    </div>
</template>

<script>
export default {
  data() {
    return {
      languages: ["en", "it", "de", "fr"]
    }
  },
  props: {
    card: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/cardStyle.scss";
</style>