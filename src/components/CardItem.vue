<template>
  <div class="card">
    <img :src="pokemon.imgUrl" alt="picture of pokemon">
    <div>
      <div class="types">
        <TypeItem v-for="t in pokemon.type" :key="t" :type="t"></TypeItem>
      </div>
      <div class="name">Name</div>
    </div>
  </div>
</template>

<script>
import TypeItem from './TypeItem.vue';
export default {
    name: "CardItem",
    props: {
        pokemon: Object
    },
    components: { TypeItem }
}
</script>

<style lang="scss" scoped>

.card {
    border: 1px solid black;
    border-radius: 5px;
    width: 18%;
    // height: 30px;
    margin-top: 20px;
    padding: 10px;

    &:hover{
      cursor: pointer;
      border-color: red;
    }

    img {
      width: 100%;
    }

    .types {
      display: flex;
    }
}

</style>