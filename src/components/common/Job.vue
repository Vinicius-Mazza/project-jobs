<template>
  <div class="card">
    <div class="card-header bg-dark text-white">{{ title }}</div>
    <div class="card-body">
      <p>{{ description }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Salário: R$ {{ salary }} | modalidade: {{ model }} | Tipo: {{ type }} | Publicação: {{ publish }}</small>
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
    }
  }
</script>
