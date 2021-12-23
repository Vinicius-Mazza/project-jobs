<template>
  <div class="h-100 p-5 bg-light border rounded-3">
    <h2>Pesquisar Vagas</h2>
    <div class="row">
      <div class="col">
        <div class="form-group">
          <label>Título da vaga</label>
          <input type="text" class="form-control" v-model="title" placeholder="Pesquise por palavras chaves, por exemplo 'PHP', 'Pleno', 'Analista'">
          <small class="form-text text-muted">Informe palavras que estejam relacionadas com o título da vaga que você procura</small>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <button class="btn btn-outline-dark mt-2" type="button" @click="searchJob()">Buscar</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'SearchJobs',
    data: () => ({
      title: ''
    }),
    methods: {
      searchJob() {
        this.emitter.emit('filter', { 
          title: this.title 
        })
      }
    }
  }
</script>