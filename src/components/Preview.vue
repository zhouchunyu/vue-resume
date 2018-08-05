<template>
  <div>
    {{resume.profileInfo[0] && resume.profileInfo[0].name}}
  </div>
</template>

<script>
export default {
  name: 'Preview',
  props: {
    resume: {
      type: Object
    }
  }
}
</script>

<style scoped>
div {
  border: 1px solid green;
}
</style>
