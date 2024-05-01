<template>
  
  <topo @navegar="componente = $event"></topo>
  <alerta v-if="exibirAlerta"></alerta>
  <vagas-favoritas></vagas-favoritas>
  <conteudo :conteudo="componente"></conteudo>
</template>

<script>
import Conteudo from './components/Layouts/Counteudo.vue'
import Topo from './components/Layouts/Topo.vue'
import VagasFavoritas from './components/Comuns/VagasFavoritas.vue'
import Alerta from './components/Comuns/Alerta.vue'
export default {
  name: 'App',
  methods: {
    acao(p) {
      console.log(p)
    }
  },
  data: () => ({
    componente: 'Home',
    exibirAlerta: false

  }),
  components: {
    Conteudo,
    Topo,
    VagasFavoritas,
    Alerta
  },
  mounted() {
    this.emitter.on('alerta', () =>{
      this.exibirAlerta = true
      setTimeout(()=> this.exibirAlerta = false, 4000)
      
    })
  },
}
</script>

<style></style>
