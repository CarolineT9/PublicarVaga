<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <h4>Apresente sua vaga para milhares de profissionais e de graça</h4>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Título da Vaga</label>
        <input type="text" class="form-control" v-model="titulo" />
        <div class="form-text">
          Por exemplo: Programador JavaScript e VueJS.
        </div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Descrição</label>
        <textarea
          type="text"
          class="form-control"
          v-model="descricao"
        ></textarea>
        <div class="form-text">Informe os detalhes da vaga.</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label for="" class="form-label">Salário</label>
        <input type="number" class="form-control" v-model="salario" />
        <div class="form-text">Informe o salário.</div>
      </div>
      <div class="col">
        <label for="" class="form-label">Modalidade</label>
        <select type="number" class="form-select" v-model="modalidade">
          <option value="" disabled>Selecione</option>
          <option value="1">Home Office</option>
          <option value="2">Presencial</option>
        </select>
        <div class="form-text">
          Informe onde as atividades serão realizadas.
        </div>
      </div>
      <div class="col">
        <label for="" class="form-label">Tipo</label>
        <select type="number" class="form-select" v-model="tipo">
          <option value="" disabled>Selecione</option>
          <option value="1">CLT</option>
          <option value="2">PJ</option>
        </select>
        <div class="form-text">Informe o tipo de contratação.</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <button type="submit" class="btn btn-primary" @click="salvarVaga()">
          Cadastrar
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PublicarVagas",
  data: () => ({
    titulo: "",
    descricao: "",
    salario: "",
    modalidade: "",
    tipo: "",
  }),

  methods: {
    salvarVaga() {
      let tempoDecorrido = Date.now();
      let dataAtual = new Date(tempoDecorrido);

      let vagas = JSON.parse(localStorage.getItem("vagas"));

      if (!vagas) vagas = [];
      vagas.push({
        titulo: this.titulo,
        descricao: this.descricao,
        salario: this.salario,
        modalidade: this.modalidade,
        tipo: this.tipo,
        publicacao: dataAtual.toLocaleString("pt-BR"),
      });

      //localStorage.setItem("vagas", JSON.stringify(vagas));
      this.emitter.emit('alerta')
      this.reseteFormularioCadastroVaga();
    },
    reseteFormularioCadastroVaga() {
      this.titulo = "";
      this.descricao = "";
      this.salario = "";
      this.modalidade = "";
      this.tipo = "";
    },
  },
};
</script>

<style>
</style>