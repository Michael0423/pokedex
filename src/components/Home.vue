<template>
  <div class="nav-bar">
    <div>
      <a href="#">Sign Up</a>
    </div>
    <div>
      <a href="#">Sign In</a>
    </div>
  </div>
  <SearchBar @filter="filter"></SearchBar>
  <div class="card-list">
    <CardItem v-for="(p, index) in list" :key="index" :pokemon="p"></CardItem>
  </div>
  <div class="btn-area">
    <button @click="onPrev">上一頁</button>
    <button @click="onNext">下一頁</button>
  </div>
</template>

<script>
import CardItem from "./CardItem.vue";
import SearchBar from "./SearchBar.vue";
import Pokemons from "../data.js";

export default {
  name: "HomePage",
  components: {
    CardItem,
    SearchBar   
  },
  data: function () {
    let list = Pokemons.data.slice(0, 8);
    return {
      Pokemons: Pokemons.data,
      list,
      page: 1,
      size: 8,
      search: {}
    };
  },
  created() {},
  methods: {
    refreash() {
      let s = (this.page - 1) * this.size;

      this.list = this.Pokemons.slice(s, s + this.size);
    },
    onPrev() {
      if (this.page - 1 > 0) {
        this.page--;
      }
      this.refreash();
    },
    onNext() {
      if (this.page + 1 <= this.Pokemons.length / this.size + 1) {
        this.page++;
      }
      this.refreash();
    },
    filter(search){
        this.search = search;
        this.refreash();
    }
  },
};
</script>

<style lang="scss" scoped>
.nav-bar {
  display: flex;
  justify-content: flex-end;

  > div {
    margin: 0 5px;
  }
}

.card-list {
  width: 80%;
  max-width: 1800px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.btn-area {
  display: flex;
  justify-content: space-between;
}
</style>