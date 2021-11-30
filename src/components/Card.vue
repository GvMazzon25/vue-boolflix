<template>
  <section class="box">
          <ul>
                <li><h3>Titolo: {{ title }}</h3></li>
                <li class="img-box">
                    <img :src="image" :alt="originalTitle">
                </li>
                <li>Titolo Originale: {{ originalTitle }}</li>
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
    name: 'Card',
    props: {
        image: Image,
        title: String,
        originalTitle: String,
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
  @import '@/style/main.scss';
</style>