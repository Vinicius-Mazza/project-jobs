<template>
  <Home />
  <PostJob />
</template>

<script>
  import { Home, PostJob } from '@/components/views'
  
  export default {
    name: "Content",
    components: {
      Home, 
      PostJob
    }
  }
</script>

<style></style>