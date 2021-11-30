<template>
  <section class="box">
          <ul>
                <li><h3>Titolo: {{ name }}</h3></li>
                <li class="img-box">
                    <img :src="image" :alt="originalName">
                </li>
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
        image: Image,
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
.img-box{
           width: 100px;
           height: 100px;
           background-color: black;
            position: relative;
            left: 85%;
           img{
               width: 100%;
               height: 100%;
               background-repeat: no-repeat;
               background-size: contain;
              

           }
       }
</style>