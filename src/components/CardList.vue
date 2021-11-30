<template>
<section>
  <div class="card" 
       v-for="item in list"
       :key="item.id"
  >
    <Card 
         :title='item.title'
         :originalTitle='item.original_title'
         :originalLanguage='item.original_language'
         :vote='item.popularity'
    />
  </div>
</section>
</template>

<script>
import Card from '@/components/Card.vue'

export default {
    name: 'CardList',
    components: {
      Card,
    },
    props: {
        list: Array,
    }
}
</script>

<style lang='scss'>

</style>

