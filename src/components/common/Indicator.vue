<template>
  <div class="h-100 p-5 rounded-3 border bg-dark text-white">
    <p>{{ title }}</p>
    <h2>{{ quant }}</h2>
  </div>
</template>

<script>
  export default {
    name: 'Indicator',
    props: {
      title: String,
      quant: Number
    }
  }
</script>
