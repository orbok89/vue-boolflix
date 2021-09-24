<template>
  <div>
     <div>{{ lista_titoli_locandina.title}}</div>
     <div>{{lista_titoli_locandina.original_title}}</div>
    <div>{{lista_titoli_locandina.original_language}}</div>
    <div> {{lista_titoli_locandina.vote_average}}</div>
  </div>
</template>

<script>
export default {
    name:'Locandina',
    props:['lista_titoli_locandina']
}
</script>

<style>

</style>