<template>
  <main>
    <div class="container py-4">
      <div class="card-container d-flex flex-wrap justify-content-center">
        <div class="mt-2" v-for="movie in filterAll" :key="movie.id">
          <card-content :card="movie" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import CardContent from "./CardContent.vue";
export default {
  components: {
    CardContent
    },
  props: {
    filterAll: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  min-height: 100vh;
  height: 100%;
  background: rgb(0, 0, 0);

  h4 {
    color: #fff;
  }
}
</style>