<template>
  <div :class="styleIndicator">
    <p>{{ title }}</p>
    <h2>{{ quant }}</h2>
  </div>
</template>

<script>
  export default {
    name: 'Indicator',
    props: {
      title: String,
      quant: Number,
      bg: String,
      color: String
    },
    computed: {
      styleIndicator() {
        return `h-100 p-5 rounded-3 border ${this.bg} ${this.color}`
      }
    }
  }
</script>
