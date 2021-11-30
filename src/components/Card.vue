<template>
  <section class="box">
          <ul>
                <li><h3>Titolo: {{ title }}</h3></li>
                <li>Titolo Originale: {{ originalTitle }}</li>
                <li>Lingua: {{ language }}</li>
                <li>Voto: {{ vote }}</li>
          </ul>
  </section>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: String,
        originalTitle: String,
        language: String,
        vote: Number,
    }
}
</script>

<style lang='scss'>
  @import '@/style/main.scss';
</style>