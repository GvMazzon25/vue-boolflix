<template>
  <section>
  <div class="card" 
       v-for="item in list2"
       :key="item.id"
  >
    <CardSeries 
         :title='item.title'
         :originalTitle='item.original_title'
         :language='item.original_language'
         :vote='item.popularity'
    />
  </div>
</section>
</template>



<script>
import CardSeries from '@/components/CardSeries.vue'

export default {
    name: 'SeriesList',
    components: {
      CardSeries,
    },
    props: {
        list2: Array,
    }
}
</script>

<style>

</style>