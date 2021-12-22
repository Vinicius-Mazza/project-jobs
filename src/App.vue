<template>
  <div>
    <FavoritesJobs />
    <Top @navigate="component = $event" />
    <Alert v-if="showAlert" />
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
      showAlert: false
    }),
    components: {
      Content,
      Top,
      FavoritesJobs,
      Alert
    },
    mounted() {
      this.emitter.on('alert', () => {
        this.showAlert = true
        setTimeout(() => this.showAlert = false, 4000)
      })
    }
  }
</script>

<style></style>
