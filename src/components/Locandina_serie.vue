<template>
  <div>
    <img :src="`https://image.tmdb.org/t/p/w200${lista_titoli_locandina_serie.poster_path}`"  alt="">
     <div>{{ lista_titoli_locandina_serie.name}}</div>
     <div>{{lista_titoli_locandina_serie.original_name}}</div>
     <country-flag :country='get_flag(lista_titoli_locandina_serie.original_language)' size='small'/>
     <div> {{star(lista_titoli_locandina_serie.vote_average)}}</div>
     <div v-for="(prova, index) in star(lista_titoli_locandina_serie.vote_average)" :key="index"> <font-awesome-icon icon="star" /> 1</div>
     <div>prova prova</div>
  </div>
</template>

<script>
 

import CountryFlag from 'vue-country-flag'
export default {
    name:'Locandina_serie',
     components: {
        CountryFlag,
    },
    props:['lista_titoli_locandina_serie'],
    methods:{
      get_flag(lingua){
        if(lingua == "en")return "gb"
        return lingua
      },
         star(numero){
        let stelle= Math.ceil((numero/2));
        return stelle

      }
    }
}
</script>

<style>

</style>