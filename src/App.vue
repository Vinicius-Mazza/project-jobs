<template>
  <div>
    <FavoritesJobs />
    <Top @navigate="component = $event" />
    <Alert v-if="showAlert" :type="alert.type">
      <template v-slot:title>
        <h5>{{ alert.title }}</h5>
      </template>
      <p>{{ alert.description }}</p>
    </Alert>
    <Content :content="component" />
  </div>
</template>

<script>
  import { Top, Content } from "@/components/layouts"
  import { FavoritesJobs, Alert } from "@/components/common"

  export default {
    name: "App",
    data: () => ({
      component: 'Home',
      showAlert: false,
      alert: {
        title: '',
        description: '',
        type: ''
      }
    }),
    components: {
      Content,
      Top,
      FavoritesJobs,
      Alert
    },
    mounted() {
      this.emitter.on('alert', (a) => {
        this.alert = a
        this.showAlert = true
        setTimeout(() => this.showAlert = false, 4000)
      })
    }
  }
</script>

<style></style>
