<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <h4>Apresente a sua vaga para milhares de profissionais</h4>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label class="form-label">Título da Vaga</label>
        <input type="text" class="form-control" v-model="title">
        <div class="form-text">Por exemplo: Programador JavaScript Vuejs.</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label class="form-label">Descrição</label>
        <textarea type="text" class="form-control" v-model="description"></textarea>
        <div class="form-text">Informe os detalhes da vaga.</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <label class="form-label">Salário</label>
        <input type="number" class="form-control" v-model="salary">
        <div class="form-text">Informe o salário</div>
      </div>
      <div class="col">
        <label class="form-label">Modalidade</label>
        <select class="form-control" v-model="model">
          <option value="" disabled>--Selecione</option>
          <option value="home-office">Home Office</option>
          <option value="presencial">Presencial</option>
        </select>
        <div class="form-text">Informe onde as atividades serão realizadas.</div>
      </div>
      <div class="col">
        <label class="form-label">Tipo de contratação</label>
        <select class="form-control" v-model="type">
          <option value="" disabled>--Selecione</option>
          <option value="pj">PJ</option>
          <option value="clt">CLT</option>
        </select>
        <div class="form-text">Informe o tipo de contratação.</div>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col">
        <button type="submit" class="btn btn-primary" @click="saveJob()">Cadastrar</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'PostJob',
    data: () => ({
      title: '',
      description: '',
      salary: 0,
      model: '',
      type: '',
      publish: ''
    }),
    methods: {
      saveJob() {
        let jobs = JSON.parse(localStorage.getItem('jobs'))
        if(!jobs) jobs = []

        jobs.push({
          title: this.title,
          description: this.description,
          salary: this.salary,
          model: this.model,
          type: this.type,
          publish: this.publish
        })

        localStorage.setItem('jobs', JSON.stringify(jobs))
      }
    }
  }
</script>
<style></style>
