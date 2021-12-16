<template>
   <div class="container py-4">
    <div class="row">
      <div class="col">
        <SearchJobs />
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-4">
        <Indicator title="Vagas Abertas" :quant="25" bg="bg-dark" color="text-light" />
      </div>
      <div class="col-4">
        <Indicator title="Profissionais Cadastrados" :quant="125" bg="bg-dark" color="text-light" />
      </div>
      <div class="col-4">
        <Indicator title="Visitantes Online" :quant="15" bg="bg-white" color="text-dark" />
      </div>
    </div>
  </div>
</template>

<script>
  import { SearchJobs, Indicator } from '@/components/common'

  export default {
    name: 'Home',
    components: {
      SearchJobs,
      Indicator
    }
  }
</script>
<style></style>
