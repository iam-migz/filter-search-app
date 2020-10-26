<template>
  <div id="search">
      <input v-model="searchData" @keyup.enter="send" type="text" placeholder="Search Category or Item...">
  </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      searchData: ''
    }
  },
  methods: {
    send(){
      this.$emit('new-input', this.searchData)
    }
  }
}
</script>

<style scoped>
#search input[type='text']{
    width: 100%;
    height: 50px;
    padding-left: 50px;
    border: 0;
    border-bottom: 1px solid grey;
}
</style>