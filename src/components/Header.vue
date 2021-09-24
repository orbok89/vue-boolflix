<template>
  <div>
      <header>
          <h1>boolflix</h1>
          <input v-model="parola_chiesta" type="text" placeholder="cerca film" @keydown.enter="$emit('collegamento', parola_chiesta) ">
      </header>
  </div>
</template>

<script>
export default {
name: 'Header',
data(){
    return{
        parola_chiesta: ''
    }
},
methods:{
    
}
}
</script>

<style  scoped lang="scss">
header{
    width: 100%;
    height: 100px;
    background-color: black;
}
h1{
    color: red;
}
</style>