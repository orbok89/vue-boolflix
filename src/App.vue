<template>
  <div id="app">
   <Header @collegamento="get_lista_film"/>
   <Main
    :lista_titoli_ridotta_main="lista_titoli_ridotta"
    :lista_titoli_ridotta_serie="lista_titoli_ridotta_serie" />
 
  
<div>
 
 
</div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      chiave:'4fcb43fd877d3ef9800ae2234b49c5ff',
      url_film: 'https://api.themoviedb.org/3/search/movie?api_key=',
      url_serie:'https://api.themoviedb.org/3/search/tv?api_key=',
      lista_titoli_ridotta:'',
      lista_titoli_ridotta_serie:''
    }
  },
  methods:{
    get_lista_film(filtro_parola){
      
      axios.get(this.url_film+this.chiave+'&query='+filtro_parola).then(res=>{
        this.lista_titoli_ridotta=res.data.results
        
      })
      axios.get(this.url_serie+this.chiave+'&query='+filtro_parola).then(res=>{
        this.lista_titoli_ridotta_serie=res.data.results
        
      })
    }
  }
}
</script>

<style scoped  lang="scss">

</style>
