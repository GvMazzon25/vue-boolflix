<template>
  <section class="box">
      <img 
            v-if="poster"
           :src="`https://image.tmbd.org/t/p/w342${poster}`" 
           :alt="title"
       />
      <img 
           v-else
           src="https://www.altavod.com/assets/images/poster-placeholder.png" 
           :alt="title"
      />
          <ul>
                <li><h3>Titolo: {{ name }}</h3></li>
                <li>Titolo Originale: {{ originalName }}</li>
                <li>
                    Lingua: 
                    <img 
                        v-if="isFlag"
                        :src="require(`../assets/${language}.png`)" 
                        :alt="language"
                    />
                    <span v-else>{{ language }}</span>
                </li>
                <li>Voto: {{ vote }}</li>
          </ul>
  </section>
</template>

<script>
export default {
    name: 'CardSeries',
    props: {
        poster: String,
        name: String,
        originalName: String,
        language: String,
        vote: Number,
    },
    data() {
        return {
            availableFlags: ['it','en'],
        };
    },
    computed: {
        isFlag() {
            return this.availableFlags.includes(this.language)
        }
    }
};
</script>

<style scope lang='scss'>
</style>