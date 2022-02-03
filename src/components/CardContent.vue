<template>
    <div class="card">
      <div class="back-card border border-white py-4 px-3">
        <h3>{{card.title}}</h3>
        <h6> {{card.original_title}}</h6>
        <p>Voto: {{card.vote_average}}</p>
        <span> {{card.overview}}</span>
      </div>
      <a href="#">
        <img v-if="card.poster_path !== null" :src="`https://www.themoviedb.org/t/p/original${card.poster_path}`" alt="" />
        <img v-else src="https://www.google.com/search?q=img+not+found&rlz=1C1CHBF_itIT923IT923&sxsrf=APq-WBs9jFnOm99zSM8T6ZAzAGuLPtHmOg:1643910006190&tbm=isch&source=iu&ictx=1&vet=1&fir=ChBJG83P3qpRbM%252CxVwqYIVUdXUeHM%252C_%253BqkTc8mRrKbQ6aM%252CpQqIKjZs4vn4tM%252C_%253B1Hcr6MmWtkOBSM%252CoJz1yYsIZ-24sM%252C_%253BtUViYmZcuTQJTM%252CMOD0q2t-fl_QaM%252C_%253Bgo0xj-MtnwrOJM%252Crb42RVdX5acoCM%252C_%253B89ApC80bNoogSM%252CdRQw5VngqZK0gM%252C_%253B-FeCDevOqDc4oM%252Cr8tRcZ0zWns48M%252C_%253B-pCCN7e53SUTOM%252Cr_RVBdpWxJHlNM%252C_%253B34FWtU_hLH3rqM%252CaOSrfb1eRI07SM%252C_%253BONa-5ZuFLLcwAM%252CaOmRh6XOUiIPgM%252C_&usg=AI4_-kRtKdd-9NsSLWRKqx271h8bVLKXGA&sa=X&ved=2ahUKEwir_Nf_ieT1AhWBSPEDHSUwBCcQ9QF6BAgIEAE#imgrc=-pCCN7e53SUTOM" alt="" />
      </a>
    </div>
</template>

<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/cardStyle.scss";
</style>