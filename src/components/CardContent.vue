<template>
    <div class="card">
      
      <div class="back-card py-4 px-3">
        <h3>{{card.title}}</h3>
        <h6> {{card.original_title}}</h6>

        <div class="language">
          <img v-if="languages.includes(card.original_language)" :src="require('@/assets/' + card.original_language + '.png')" alt=""/>  <!-- fixed -->
          <span v-else>Original language: {{card.original_language}}</span>
        </div>

        <div class="vote mt-2 mb-1">
            <div  v-for="(vote, index) in voteNumber" :key="index">
                <i v-if="index + 1 <= voteStar()" class="fas fa-star"></i>
                <i v-else ></i>
            </div>
        </div>
       

        <span> {{card.overview}}</span>

      </div>
      
        <img v-if="card.poster_path !== null" :src="`https://www.themoviedb.org/t/p/original${card.poster_path}`" alt="" />
        <img v-else src="@/assets/not-found.png" alt="" />
      
    </div>
</template>

<script>
export default {
  components: {
  },
  data() {
    return {
      languages: ["en", "it", "de", "fr", "ja"],
      voteNumber: ["1", "2", "3", "4", "5"],
    }
  },
  props: {
    card: Object,
  },
  methods: {
     voteStar: function () {
      if (this.card.vote_average > 0 && this.card.vote_average <= 10) {
        return Math.round(this.card.vote_average / 2);
      }
    },
  }
};
</script>

<style lang="scss" scoped>
@import "@/style/cardStyle.scss";
</style>