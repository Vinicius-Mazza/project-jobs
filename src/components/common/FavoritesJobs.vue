<template>
  <div>
    <div class="favorites">
      <button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight">Vagas favoritas</button>
    </div>
    <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
      <div class="offcanvas-header">
        <h5 id="offcanvasRightLabel">Vagas favoritadas</h5>
        <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>
      <div class="offcanvas-body">
        <ul class="list-group">
          <li class="list-group-item" v-for="(job, index) of jobs" :key="index">{{ job }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'FavoritesJobs',
    data: () => ({
      jobs: []
    }),
    mounted() {
      this.emitter.on('favoriteJob', (title) => {
        this.jobs.push(title)
      })

      this.emitter.on('disfavoriteJob', (title) => {
        let indexArray = this.jobs.indexOf(title)
        if(indexArray !== -1) this.jobs.splice(indexArray, 1)
      })
    }
  }
</script>

<style scoped>
  .favorites {
    position: absolute; 
    z-index: 1; 
    top: 70px; 
    right: 0px;
  }
</style>