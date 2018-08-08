<template>
  <div>
    <section class="profileInfo" v-if="resume.profileInfo[0]">
      <h1>{{resume.profileInfo[0].name || '请填写姓名'}}</h1>
      <div class="personalInfo">
        <span>{{resume.profileInfo[0].city || "请填写城市"}}</span>
        <span>{{`| ${resume.profileInfo[0].age || "请填写年龄"}`}}</span>
      </div>
    </section>
    <section>

    </section>
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
</style>z
