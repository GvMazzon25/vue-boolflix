<template>
<section>
  <div class="card" 
       v-for="item in list1"
       :key="item.id"
  >
    <Card 
         :image='item.poster_path'
         :title='item.title'
         :originalTitle='item.original_title'
         :language='item.original_language'
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
        list1: Array,
    }
}
</script>

<style lang='scss'>

</style>

