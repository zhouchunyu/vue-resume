<template>
  <div @dblclick="e_preview()">
    <section class="profileInfo" v-if="resume.profileInfo[0]">
      <h1>{{resume.profileInfo[0].name || '请填写姓名'}}</h1>
      <div class="personalInfo">
        <span>{{resume.profileInfo[0].city || "请填写城市"}}</span>
        <span>{{`| ${resume.profileInfo[0].age || "请填写年龄"}`}}</span>
      </div>
    </section>
    <hr>
    <section class="projects" v-if="resume.projectsExp">
      <div class="project" v-for="project in resume.projectsExp">
        {{project.date || "请填写项目日期"}}{{` | ${project.name || "请填写项目名称"}` }}{{` | ${project.content || "请填写项目内容"}`}}
      </div>
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
  },
  methods: {
    e_preview() {
      this.$emit('preview');
    }
  }
}
</script>

<style scoped>
</style>z
