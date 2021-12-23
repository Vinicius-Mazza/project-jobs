<template>
  <div :class="alertStyle(this.type)" role="alert">
    <slot name="title"></slot>
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'Alert',
    props: {
      type: String
    },
    methods: {
      alertStyle(typeAlert) {
        return {
          'success': 'alert alert-success',
          'error': 'alert alert-danger'
        }[typeAlert] || 'alert alert-success'
      }
    }
  }
</script>

<style></style>
