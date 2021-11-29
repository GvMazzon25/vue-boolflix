<template>
  <main>
      <div v-if="cardList !== null">
        <div
         v-for="card in cardList"
         :key="`card${card.id}`"
        >
            <ul>
              <li><h4>Titolo: {{card.title}}</h4></li>
              <li>Titolo Originale: {{card.original_title}}</li>
              <li>Lingua: {{card.original_language}}</li>
              <li>Voto: {{card.popularity}}</li>
            </ul>
        </div>
      </div>
        <div v-else>Loading...</div>
  </main>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Main',
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
               this.cardList = result.data.result
             })
             .catch(err => console.log(err));
      }
    }
}
</script>

<style scoped lang='scss'>

</style>