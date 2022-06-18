<template>
  <div>
    <input type="text" v-model="keyword">
    <input type="button" value="搜尋" @click="search">
  </div>
</template>

<script>
export default {
    name: 'SearchBar',
    data: function () {
        return {
            keyword: '',
        }
    },
    methods: {
        search() {
            let search = {
                keyword: this.keyword
            }

            this.$emit('filter', search);
        }
    }
}
</script>

<style>

</style>