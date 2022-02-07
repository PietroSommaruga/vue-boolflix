<template>
  <header>
    <div class="d-flex justify-content-between align-items-center head">
      <a href=""><h1 class="text-uppercase mx-4">netflix</h1></a>
      <div>
        <input id="search-input" class="mx-2 py-1 px-2" type="text" placeholder="Search" v-model="textSearch" @keyup.enter="$emit('search', textSearch)" />
        <button id="search-btn" class=" py-1 px-3" @click="$emit('search', textSearch)">Search</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      textSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.head {
  height: 100px;
  background: rgb(41, 41, 41);
  a {
    text-decoration: none;
    color: red;
    }
  
}
</style>