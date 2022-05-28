<template>
  <div class="nav-bar">
    <div>
      <a href="#">Sign Up</a>
    </div>
    <div>
      <a href="#">Sign In</a>
    </div>
  </div>
  <div>Search Bar</div>
  <div class="card-list">
    <CardItem v-for="(p, index) in list" :key="index" :pokemon="p"></CardItem>
  </div>
</template>

<script>
import CardItem from './components/CardItem.vue'

export default {
  name: 'App',
  components: {
    CardItem
  },
  data: function() {
    return {
      list: [
        {
          id: 1,
          name: 'A',
          type: ['normal'],
          imgUrl: '#'
        },
        {
          id: 1,
          name: 'B',
          type: ['water', 'fly'],
          imgUrl: '#'
        }
      ]
    }
  },
  created() {

  }
}
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
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

</style>