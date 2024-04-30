<template>
    
        <component :is="conteudo"></component>
    
</template>

<script>
import Home from '../Views/Home.vue'
import PublicarVagas from '../Views/PublicarVagas.vue'
export default {
    name: 'Conteudo',
    props:{
      conteudo:{
        type: String,
        required: true
      }
    },
    components: {
      Home,
      PublicarVagas
  }
}
</script>

<style>

</style>