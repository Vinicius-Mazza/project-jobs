<template>
  <div class="card">
    <div class="card-header bg-dark text-white">
      <div class="row">
        <div class="col d-flex justify-content-between">
          <div>{{ title }}</div>
          <div>
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="favorite">
              <label class="form-check-label">Favoritar vaga</label>
            </div>
          </div>
        </div>
      </div>
    </div>
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
    data: () => ({
      favorite: false
    }),
    watch: {
      favorite(newValue) {
        newValue ? this.emitter.emit('favoriteJob', this.title) : this.emitter.emit('disfavoriteJob', this.title)
      }
    },
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
