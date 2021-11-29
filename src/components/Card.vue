<template>
  <div>
        <ul>
              <li><h3>Titolo: {{title}}</h3></li>
              <li>Titolo Originale: {{originalTitle}}</li>
              <li>Lingua: {{originalLanguage}}</li>
              <li>Voto: {{vote}}</li>
        </ul>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: String,
        originalTitle: String,
        originalLanguage: String,
        vote: Number,
    }
}
</script>

<style lang='scss'>
  @import '@/style/main.scss';
</style>