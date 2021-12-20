<template>
   <div class="container py-4">
    <div class="row">
      <div class="col">
        <SearchJobs />
      </div>
    </div>
    <div class="row mt-5" v-for="(job, index) of jobs" :key="index">
      <div class="col">
        <Job v-bind="job" />
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-4" v-for="(indicator, index) of indicators" :key="index">
        <Indicator v-bind="indicator"/>
      </div>
    </div>
  </div>
</template>

<script>
  import { SearchJobs, Job, Indicator } from '@/components/common'

  export default {
    name: 'Home',
    data: () => {
      return {
        jobs: [],
        indicators: [
          {
            title:"Vagas Abertas", 
            quant: 25,
            bg: "bg-dark",
            color: "text-light"
          },
          {
            title:"Profissionais Cadastrados", 
            quant: 125,
            bg: "bg-dark",
            color: "text-light"
          },
          {
            title:"Visitantes Online", 
            quant: 15,
            bg: "bg-white",
            color: "text-dark"
          }
        ]
      }
    },
    components: {
      SearchJobs,
      Job,
      Indicator
    },
    activated() {
      this.jobs = JSON.parse(localStorage.getItem("jobs"))
    }
  }
</script>
<style></style>
