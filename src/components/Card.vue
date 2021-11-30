<template>
  <div class="card" 
       v-for="item in list"
       :key="item.id"
  >
    <div class="box">
          <ul>
                <li><h3>Titolo: {{ item.title }}</h3></li>
                <li>Titolo Originale: {{ item.originalTitle }}</li>
                <li>Lingua: {{ item.originalLanguage }}</li>
                <li>Voto: {{ item.vote }}</li>
          </ul>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        list: Array,

    }
}
</script>

<style lang='scss'>
  @import '@/style/main.scss';
</style>

