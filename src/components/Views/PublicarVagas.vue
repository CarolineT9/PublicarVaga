<template>
    <div class="container">
        <div class="h-100 bg-light p-5 border rounded-3">
    <h2>Pesquisar vagas</h2>
    <div class="row">
      <div class="col">
        <div class="form-group">
          <label for="">Título da vaga</label>
          <input
            type="text"
            class="form-control"
            placeholder="Pesquise por palavras chaves ex: Php, JavaScript, Sênior..."
          />
          <small class="form-text text-muted"
            >Informe palavras que estejam relacionadas como título da vaga que
            você procura.</small
          >
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <button class="btn btn-outline-dark mt-2" type="button">Buscar</button>
      </div>
    </div>
  </div>
    </div>

</template>

<script>
export default {
    name: 'PublicarVagas'
}
</script>

<style>

</style>