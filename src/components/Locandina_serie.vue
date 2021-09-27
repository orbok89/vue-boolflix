<template>
  <div>
     <div>{{ lista_titoli_locandina_serie.name}}</div>
     <div>prova prova</div>
  </div>
</template>

<script>
 


export default {
    name:'Locandina_serie',
     components: {
        
    },
    props:['lista_titoli_locandina_serie'],
    methods:{
      get_flag(lingua){
        if(lingua == "en")return "gb"
        return lingua
      }
    }
}
</script>

<style>

</style>