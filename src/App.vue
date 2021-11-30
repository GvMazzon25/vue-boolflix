<template>
<div class="app">
  <Header @search="performSearch"/>
  <main>
    <section class="film">
      <h2>Film</h2>
    <CardList  
     :list1="movieList"
  />
  </section>
  <section class="serie">
    <h2>Serie TV</h2>
    <SeriesList  
     :list2="seriesList"
  />
  </section>
  </main>
</div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import CardList from '@/components/CardList.vue';
import SeriesList from '@/components/SeriesList.vue';

export default {
  name: 'App',
  components: {
    Header,
    CardList,
    SeriesList,
  },
  data() {
    return {
      movieList: [],
      seriesList: []
    };
  },
  methods: {
    performSearch(searchText) {
      console.log(searchText);

      if (searchText !== '') {
         axios
             .get('https://api.themoviedb.org/3/search/movie?', {
                  params: {
                    api_key:'e99307154c6dfb0b4750f6603256716d',
                    query: searchText,
                    language:'it-IT',
                },
             })
             .then(result => {
               this.movieList = result.data.results;
             })
             .catch(err => console.log(err));

          axios
             .get('https://api.themoviedb.org/3/search/tv?', {
                  params: {
                    api_key:'e99307154c6dfb0b4750f6603256716d',
                    query: searchText,
                    language:'it-IT',
                },
             })
             .then(result => {
               this.seriesList = result.data.results;
             })
             .catch(err => console.log(err));
      }
    },
    
  }
}
</script>

<style lang="scss">
  @import '@/style/generals.scss'; 
</style>
