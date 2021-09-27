<template>
  <div class="colore" @click="prova()">
      <div  v-for="(film, index) in lista_titoli_ridotta_main" :key="index">
          <Locandina :lista_titoli_locandina="film" />
      </div>
      <div  v-for="(serie, i) in lista_titoli_ridotta_serie" :key="'a'+i">
          <Locandina_serie :lista_titoli_locandina_serie="serie" />
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
    .colore{
        background-color: royalblue;
        width: 100%;
        height: 200px;
    }
   
</style>