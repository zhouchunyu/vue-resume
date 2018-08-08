<template>
  <div>
    <nav>
      <ol>
        <li v-for="i in [0,1,2,3,4,5]" :class="{active: currentTab === i}" @click="currentTab = i">
          <svg class="icon" aria-hidden="true">
            <use :xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="panes">
      <li :class="{active: currentTab === 0}">
        <Experiences :labels="profile" title="个人信息" :experiences="resume.profileInfo"></Experiences>
      </li>
      <li :class="{active: currentTab === 1}">
        <Experiences :labels="workingHistory" title="工作经历" add cancel :experiences="resume.workingExp"></Experiences>
      </li>
      <li :class="{active: currentTab === 2}">
        <Experiences :labels="learningHistory" title="学习经历" add cancel :experiences="resume.learningExp"></Experiences>
      </li>
      <li :class="{active: currentTab === 3}">
        <Experiences :labels="projects" title="项目经历" add cancel :experiences="resume.projectsExp"></Experiences>
      </li>
      <li :class="{active: currentTab === 4}">
        <Experiences :labels="projects" title="联系方式" :experiences="resume.contactInfo"></Experiences>
      </li>
    </ol>
  </div>
</template>

<script>
import Experiences from './Experiences';

export default {
  name: 'Editor',
  data(){
    return {
      currentTab: 0,
      icons: ['credentials', 'working', 'learning', 'project', 'contact'],
      profile: {name: '姓名',city: '城市', age: '年龄'},
      workingHistory: {company: '公司名称', content: '工作内容'},
      learningHistory: {school: '学校', date: '日期', master: '专业'},
      projects: {name: '项目名称', date: '日期', content: "项目内容"},
      contact: {phone: '手机号码', "e-mail": '邮箱地址'},
    }
  },
  props: {
    resume: {
      type: Object
    }
  },
  components: {
    Experiences
  }
}
</script>


<style lang="scss" scoped>
.editor{
  width: 40em;
  margin: 16px 8px 16px 16px;
  background-color: white;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.5);
  border-rddsadius: 4px;
  display: flex;
  color: white;
}

nav > ol{
  display: flex;
  flex-direction: column;
  height: 100%;
  background-color: black;
}

nav > ol > li > svg{
  width: 2em;
  height: 2em;
  margin: 16px 24px;
}

nav > ol > li.active {
  background-color: white;
  color: black;
}

.panes{
  flex: 1;
  overflow: auto;
}

.panes > li {
  display: none;
}

.panes > li.active{
  display: block;
  color: black;
}

.panes > li > h2 {
  padding: 16px;
}

.label {
  padding: 8px 32px;
}

</style>
