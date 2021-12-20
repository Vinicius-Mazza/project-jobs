<template>
  <div>
    <Top @navigate="component = $event" />
    <Content :content="component" />
  </div>
</template>

<script>
import { Top, Content } from "@/components/layouts"

export default {
  name: "App",
  data: () => ({
    component: 'Home'
  }),
  components: {
    Content,
    Top
  }
};
</script>

<style></style>
