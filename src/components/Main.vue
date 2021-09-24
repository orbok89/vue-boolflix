<template>
  <div class="colore" @click="prova()">
      <div  v-for="(film, index) in lista_titoli_ridotta_main" :key="index">
          <Locandina :lista_titoli_locandina="film" />
      </div>
  </div>
</template>

<script>
import Locandina from './Locandina.vue'

export default {
    name:'Main',
    components: {
        Locandina
    },
    
    methods:{
    
    },
    props:['lista_titoli_ridotta_main']
}
</script>

<style scoped lang="scss">
    .colore{
        background-color: royalblue;
        width: 100%;
        height: 200px;
    }
   
</style>