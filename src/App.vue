<template>
  <div>
    <FavoritesJobs />
    <Top @navigate="component = $event" />
    <Content :content="component" />
  </div>
</template>

<script>
import { Top, Content } from "@/components/layouts"
import { FavoritesJobs } from "@/components/common"

export default {
  name: "App",
  data: () => ({
    component: 'Home'
  }),
  components: {
    Content,
    Top,
    FavoritesJobs
  }
};
</script>

<style></style>
