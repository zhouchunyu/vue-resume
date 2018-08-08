<template>
  <div>
    <div class="logg">
      Vue Resume
    </div>
    <div class="actions">
      <el-button type="primary">登陆</el-button>
      <el-button>注册</el-button>
      <el-button @click="e_preview()">预览</el-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopBar',
  props: {
    previewMode: {
      type: Boolean
    }
  },
  methods: {
    e_preview() {
      this.$emit('preview');
    }
  }
}
</script>

<style scoped>
</style>
