<template>
  <vagas-favoritas></vagas-favoritas>
  <topo @navegar="componente = $event"></topo>
  <conteudo :conteudo="componente"></conteudo>
</template>

<script>
import Conteudo from './components/Layouts/Counteudo.vue'
import Topo from './components/Layouts/Topo.vue'
import VagasFavoritas from './components/Comuns/VagasFavoritas.vue'
export default {
  name: 'App',
  methods: {
    acao(p) {
      console.log(p)
    }
  },
  data: () => ({
    componente: 'Home',

  }),
  components: {
    Conteudo,
    Topo,
    VagasFavoritas
  }
}
</script>

<style></style>
