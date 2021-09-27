<template>
  <div>
    <img :src="`https://image.tmdb.org/t/p/w200${lista_titoli_locandina.poster_path}`"  alt="">
     <div>{{ lista_titoli_locandina.title}}</div>
     <div>{{lista_titoli_locandina.original_title}}</div>
    <country-flag :country='get_flag(lista_titoli_locandina.original_language)' size='small'/>
    <div> {{star(lista_titoli_locandina.vote_average)}}</div>
  </div>
</template>

<script>
import CountryFlag from 'vue-country-flag'


export default {
    name:'Locandina',
     components: {
        CountryFlag,
    },
    props:['lista_titoli_locandina'],
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