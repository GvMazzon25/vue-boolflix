<template>
  <main>
      <div v-if="cardList !== null">
        <div
         v-for="card in cardList"
         :key="`card${card.id}`"
        >
           <Card 
              :title='card.title'
              :originalTitle= 'card.original_title'
              :originalLanguage= 'card.original_language'
              :vote= 'card.popularity'
           />
        </div>
      </div>
        <div v-else>Loading...</div>
  </main>
</template>

<script>

import Card from '@/components/Card.vue'

export default {
    name: 'Main',
    components: {
        Card,
    },
    data() {
      return {
        cardList: null,
      }
    },
    created() {
      this.getCards();
    },
    methods: {
      getCards() {
        axios
             .get('https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+futuro')
             .then(result =>{
               console.log(result.data);
               this.cardList = result.data.results
             })
             .catch(err => console.log(err));
      }
    }
}
</script>

<style scoped lang='scss'>
   @import '@/style/main.scss';
</style>