<template>
  <div class="container">
      <div>
          film
      </div>
     <div class="flex">
          <div  v-for="(film, index) in lista_titoli_ridotta_main" :key="index">
          <Locandina :lista_titoli_locandina="film" />
      </div>
      <div>
           serie tv
      </div>
     </div>
     <div class="flex">
          <div  v-for="(serie, i) in lista_titoli_ridotta_serie" :key="'a'+i">
          <Locandina_serie :lista_titoli_locandina_serie="serie" />
      </div>
     </div>
     
  </div>
</template>

<script>
import Locandina from './Locandina.vue'
import Locandina_serie from './Locandina_serie.vue'

export default {
    name:'Main',
    components: {
        Locandina,
        Locandina_serie
    },
    
    methods:{
    
    },
    props:['lista_titoli_ridotta_main', 'lista_titoli_ridotta_serie']
}
</script>

<style scoped lang="scss">
   .flex{
       display: flex;
       flex-wrap: wrap;
   }
   .container{
       width: 100%;
       background-color:gray ;
   }
   
</style>