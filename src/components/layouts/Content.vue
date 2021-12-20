<template>
  <div>
    <keep-alive>
      <component :is="content" />
    </keep-alive>
  </div>
</template>

<script>
  import { Home, PostJob } from '@/components/views'
  
  export default {
    name: "Content",
    components: {
      Home, 
      PostJob
    },
    props: {
      content: String
    }
  }
</script>

<style></style>