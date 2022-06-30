<template>
  <div>每頁筆數:<select v-model="size" @change="changeSize">
      <option value="8">8</option>
      <option value="10">10</option>
      <option value="50">50</option>
      <option value="100">100</option>
    </select></div>

  <div class="btn-area">
    <button @click="onPrev">上一頁</button>
    <button @click="onNext">下一頁</button>
  </div>

  <div class="card-list">
    <CardItem v-for="p in list" :key="p.id + '-' + p.zukan_sub_id" :pokemon="p"></CardItem>
  </div>

</template>

<script>
import CardItem from "./CardItem.vue";
import Pokemons from "../data.js";

export default {
  name: "HomePage",
  components: {
    CardItem,
  },
  data: function () {
    return {
      Pokemons: Pokemons.data,
      list: [],
      page: 1,
      size: 8,
      search: {
        keyword: ''
      }
    };
  },
  mounted() {
    this.refreash();
  },
  methods: {
    refreash() {
      let keyword = this.search.keyword;
      let size = +this.size;
      let s = (this.page - 1) * size;
      let filterData = (keyword)
        ? this.Pokemons.filter(e => e.name.indexOf(keyword) > -1)
        : this.Pokemons;
      this.list = filterData.slice(s, s + size);
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
    filter(search) {
      this.search = search;
      this.refreash();
    },
    changeSize() {
      this.page = 1;
      this.refreash();
    }
  },
};
</script>

<style lang="scss" scoped>
.nav-bar {
  display: flex;
  justify-content: flex-end;

  >div {
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