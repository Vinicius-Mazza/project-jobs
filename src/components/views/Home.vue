<template>
   <div class="container py-4">
    <div class="row">
      <div class="col">
        <SearchJobs />
      </div>
    </div>
    <div class="row mt-5" v-for="(job, index) of jobs" :key="index">
      <div class="col">
        <Job
          :title="job.title"
          :description="job.description"
          :salary="job.salary"
          :model="job.model"
          :type="job.type"
          :publish="job.publish"
        />
      </div>
    </div>
    <div class="row mt-5">
      <div class="col-4" v-for="(indicator, index) of indicators" :key="index">
        <Indicator 
          :title="indicator.title" 
          :quant="indicator.quant" 
          :bg="indicator.bg" 
          :color="indicator.color" 
        />
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
        jobs: [
          {
            title: 'Analista Programador PHP Pleno',
            description: 'Profissional com conhecimentos em PHP, Laravel e MySQL. Necessário 3 anos de experiências. Atuará na manutenção de sistemas legados da empresa.',
            salary: 6000,
            model: 'Home Office',
            type: 'PJ',
            publish: '2021-10-10'
          },
          {
            title: 'Programador JavaScript Angular',
            description: 'Profissional com conhecimentos avançados em JavaScript e Angular.',
            salary: 5000,
            model: 'Presencial',
            type: 'CLT',
            publish: '2021-10-07'
          },
          {
            title: 'Programador JavaScript Vue',
            description: 'Profissional com conhecimentos avançados em JavaScript e Vue.',
            salary: 5000,
            model: 'Home Office',
            type: 'CLT',
            publish: '2021-10-06'
          },
          {
            title: 'Analista de Banco de Dados Sênior',
            description: 'Domínio dos bancos de dados SQL Server, Oracle, Postgre e MySQL',
            salary: 9000,
            model: 'Presencial',
            type: 'PJ',
            publish: '2021-10-06'
          },
          {
            title: 'Programador Web Júnior',
            description: 'Conhecimentos básicos em HTML, CSS, JavaScript, Bootstrap, PHP e MySQL',
            salary: 3000,
            model: 'Presencial',
            type: 'CLT',
            publish: '2021-10-05'
          }
        ],
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
    }
  }
</script>
<style></style>
