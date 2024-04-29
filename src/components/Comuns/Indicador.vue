<template>
  <div :class="estilo">
    <h2>{{ titulo }}</h2>
    <p>{{ indicador }}</p>
  </div>
</template>

<script>
export default {
  name: 'Indicador',
  props: ['titulo', 'indicador', 'bg', 'color'],
  computed: {
    estilo() {
      return `h-100 p-5 rounded-3 border ${this.bg} ${this.color}`;
    }
  }
};
</script>
