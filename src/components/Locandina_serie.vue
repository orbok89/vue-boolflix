<template>
  <div class="container1">
    <img class="prova " :src="`https://image.tmdb.org/t/p/w200${lista_titoli_locandina_serie.poster_path}`"  alt="">
    <div>Titolo: {{ lista_titoli_locandina_serie.name}}</div>
    <div>Titolo originale:{{lista_titoli_locandina_serie.original_name}}</div>
     <country-flag :country='get_flag(lista_titoli_locandina_serie.original_language)' size='small'/> 
   <div>voto:
        <span v-for="(prova, index) in star(lista_titoli_locandina_serie.vote_average)" :key="index">
         <font-awesome-icon  class="giallo" icon="star" />
    </span>
    <span v-for="(prova, index) in (5-star(lista_titoli_locandina_serie.vote_average))" :key="index">
         <font-awesome-icon   icon="star" />
    </span>
   </div>
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

<style scoped lang="scss">
    .container1{
        position: relative;
        width: 200px;
        height: 300px;
        margin: 10px;
    }
    .giallo{
        color: yellow;
         
    }
    .prova{
        position:absolute;
        z-index: 99;
    }
    .prova:hover{
        display: none;
    } 
    
</style>