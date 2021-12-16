<template>
  <div>
    <Top />
    <Content />
  </div>
</template>

<script>
import { Top, Content } from "@/components/layouts"

export default {
  name: "App",
  components: {
    Content,
    Top
  }
};
</script>

<style>
</style>
