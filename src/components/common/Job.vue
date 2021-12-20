<template>
  <div class="card">
    <div class="card-header bg-dark text-white">{{ title }}</div>
    <div class="card-body">
      <p>{{ description }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Salário: R$ {{ salary }} | modalidade: {{ getModel }} | Tipo: {{ getType }} | Publicação: {{ getPublish }}</small>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Job',
    props: {
      title: String,
      description: String,
      salary: Number,
      model: String,
      type: String,
      publish: String
    },
    computed: {
      getModel() {
        switch (this.model) {
          case 'home-office' : return 'Home Office'
          case 'presencial' : return 'Presencial'
        }
        return ''
      },
      getType() {
        switch (this.type) {
          case 'clt' : return 'CLT'
          case 'pj' : return 'PJ'
        }
        return ''
      },
      getPublish() {
        let publishDate = new Date(this.publish)
        return publishDate.toLocaleDateString('pt-Br')
      }
    }
  }
</script>
