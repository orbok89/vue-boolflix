<template>
  <div class="container1">
    <img class="prova" :src="`https://image.tmdb.org/t/p/w200${lista_titoli_locandina.poster_path}`"  alt="">
    
     <div class="cont">
        <div>{{ lista_titoli_locandina.title}}</div>
        <div>{{lista_titoli_locandina.original_title}}</div>
        <country-flag :country='get_flag(lista_titoli_locandina.original_language)' size='small'/>
        <div>voto:
        <span v-for="(prova, index) in star(lista_titoli_locandina.vote_average)" :key="index">
         <font-awesome-icon  class="giallo" icon="star" />
         </span>
         <span v-for="(prova, index) in (5-star(lista_titoli_locandina.vote_average))" :key="index">
         <font-awesome-icon   icon="star" />
          </span>
        </div>
        <div>{{lista_titoli_locandina.overview}}</div>
     </div>
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

<style scoped lang="scss">
  .container1{
        position: relative;
        width: 200px;
        height: 300px;
        margin: 10px;
        color: white;
        border-color: 1px solid white;
        background-color: black;
         
        
        overflow-y: hidden;
    }
    .giallo{
        color: yellow;
         
    }
    .prova{
        position:absolute;
        z-index: 99;
    }
    .container1:hover> img{
        display: none;
        
    } 
    .container1:hover{
      overflow-y: scroll;
    }
    .cont{
      padding: 3px;
    }
</style>