<template>
  <div class="card">
    <div>
      <img :src="pokemon.file_name" alt="picture of pokemon" width="300" height="300" />
    </div>
    <div>
      <div class="types">
        <TypeItem v-for="t in pokemon.pokemon_type_name.split(',')" :key="t" :type="t"></TypeItem>
      </div>
      <div class="name">{{ pokemon.name }}</div>
    </div>
  </div>
</template>

<script>
import TypeItem from "./TypeItem.vue";
export default {
  name: "CardItem",
  props: {
    pokemon: Object,
  },
  components: { TypeItem },
  computed: {
    img() {
      return this.pokemon.file_name;
    },

  },
};
</script>

<style lang="scss" scoped>
.card {
  border: 1px solid black;
  border-radius: 5px;
  width: calc(100% / 4 - 35px);
  min-width: 250px;
  max-width: 350px;
  margin-top: 20px;
  padding: 10px;
  display: flex;
  flex-direction: column;

  &:hover {
    cursor: pointer;
    border-color: red;
  }

  >div:first-child {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  img {
    width: 100%;
  }

  .types {
    display: flex;
  }
}
</style>