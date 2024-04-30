<template>
  <div class="row mt-5">
      <div class="col">
        <div class="card">
          <div class="card-header bg-dark text-white">{{titulo}}</div>
          <div class="card-body">
            <p>{{descricao}}</p>
          </div>
          <div class="card-footer">
            <small class="text-muted">Salario: {{ salario }} | Modalidade: {{getModalidade}} | Tipo: {{getTipo}} | Publicação: {{ publicacao }} </small>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
    name: 'Vagas',
    props: ['titulo', 'descricao', 'salario', 'modalidade', 'tipo', 'publicacao'],
    computed:{
      getModalidade(){
        switch(this.modalidade){
          case '1': return 'Home Office'
           
          case '2': return 'Presencial'
        }

        return ''
      },
      getTipo(){

        switch(this.modalidade){
          case '1': return 'CLT'
           
          case '2': return 'PJ'
        }

        return ''
      }
    }
}
</script>

<style>

</style>
