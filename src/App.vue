<template>
<div class="app">
  <Header />
  <Card  :list="movieList"/>
</div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Card from './components/Card.vue';

export default {
  name: 'App',
  components: {
    Header,
    Card,
  },
  data() {
    return {
      movieList: []
    };
  },
  methods: {
    performSearch(searchText) {
      console.log(searchText);

      if (searchText !== '') {


         axios
             .get('https://api.themoviedb.org/3/search/movie', {
                  params: {
                    api_key: 'e99307154c6dfb0b4750f6603256716',
                    query: searchText,
                    language: 'it-IT',
                },
             })
             .then(result => {
               this.movieList = result.data.results;
             })
             .catch(err => console.log(err));
      }
    }
  }
}
</script>

<style lang="scss">
  @import '@/style/generals.scss'; 
</style>
