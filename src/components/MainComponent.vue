<template>
  <main>
    <div class="container py-4">
      <div class="d-flex flex-wrap">
        <div class="m-2" v-for="movie in moviesProp" :key="movie.id">
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
    moviesProp: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  min-height: 1000px;
  height: 100%;
  background: rgb(0, 0, 0);
}
</style>