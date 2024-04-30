<template>
    <div class="container py-4">
    <div class="row">
      <div class="col">
        <PesquisarVaga></PesquisarVaga>
      </div>
    </div>
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <Vagas v-bind="vaga"></Vagas>
      </div>
      
    </div>
    
    <div class="row mt-5">
      <div class="col-4">
        <indicador titulo="Vagas abertas" indicador="100" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col-4">
        <indicador titulo="Profissionais cadastrados" indicador="225" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col-4">
        <indicador titulo="Visitantes online" :indicador="usuariosOnline" bg="bg-ligth" color="text-dark"></indicador>
      </div>
    </div>
  </div>
</template>

<script>
import Indicador from "../Comuns/Indicador.vue";
import PesquisarVaga from "../Comuns/PesquisarVaga.vue";
import Vagas from "../Comuns/Vagas.vue"

export default {
  name: "Home",
  components: {
    PesquisarVaga,
    Vagas,
    Indicador
  },
  data:() =>({
    usuariosOnline: 0,
    vagas: []
  }),
  methods:{
    getUsuariosOnoline(){
     this.usuariosOnline = Math.floor(Math.random()*100)
    }
  },
  created(){
    setInterval(this.getUsuariosOnoline, 1000) //a cada um segundo a função getusuário é chamada
  },
  mounted(){
    this.vagas = JSON.parse(localStorage.getItem('vagas'))
  }
};
</script>

<style>
</style>