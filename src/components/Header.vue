<template>
  <header>
      <h2>Boolflix</h2>
      <input type="text" 
             placeholder="Search a movie" 
             v-model.trim='searchText' 
             @keyup.enter="$emit('search', searchText)"
      />
      <button @click="$emit('search', searchText)">Click</button>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
      return {
        searchText: '',
      };
    }
}
</script>

<style scoped lang="scss">
   @import '@/style/header.scss';
</style>