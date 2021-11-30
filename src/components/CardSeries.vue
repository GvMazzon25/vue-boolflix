<template>
  <section class="box">
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

<style>

</style>