<template>
  <div>
    <nav>
      <ol>
        <li v-for="i in [0,1,2,3,4,5,6]" :class="{active: currentTab === i}" @click="currentTab = i">
          <svg class="icon" aria-hidden="true">
            <use :xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="panes">
      <li :class="{active: currentTab === 0}">
        <h2>个人信息</h2>
        <el-form>
          <el-form-item class="profile_attr" label="姓名">
            <el-input v-model="profile.name" ></el-input>
          </el-form-item>
          <el-form-item class="profile_attr" label="城市">
            <el-input v-model="profile.city"></el-input>
          </el-form-item>
          <el-form-item class="profile_attr" label="年龄">
            <el-input v-model="profile.age"></el-input>
          </el-form-item>
        </el-form>
      </li>
      <li :class="{active: currentTab === 1}"><h2>工作经历</h2></li>
      <li :class="{active: currentTab === 2}"><h2>学习经历</h2></li>
      <li :class="{active: currentTab === 3}"><h2>项目经历</h2></li>
      <li :class="{active: currentTab === 4}"><h2>获奖情况</h2></li>
      <li :class="{active: currentTab === 5}"><h2>联系方式</h2></li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'Editor',
  data(){
    return {
      currentTab: 0,
      icons: ['credentials', 'working', 'learning', 'project', 'medal', 'contact'],
      profile: {name: '', age: '', city: ''}
    }
  },
  methods: {
    onSubmit(){
      console.log(this.profile)
    }
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

.profile_attr {
  padding: 16px;
}

</style>
