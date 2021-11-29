<template>
  <main>
      <ul>
          <li><h4>Titolo:</h4></li>
          <li>Titolo Originale:</li>
          <li>Lingua</li>
          <li>Voto</li>
      </ul>
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
             .get('https://api.themoviedb.org/3/movie/550?api_key=e9578c42c322fd364bb6266a886f6239&query=Fight+Club&language=in-IT')
             .then(result =>{
               console.log(result.data);
               this.cardList = result.data
             })
             .catch(err => console.log(err));
      }
    }
}
</script>

<style scoped lang='scss'>

</style>