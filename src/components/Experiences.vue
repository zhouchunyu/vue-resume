<template>
  <div>
    <h2>{{title}}</h2>
    <div class="experiences" v-for="(experience, index) in experiences">
      <el-form>
        <div  v-for="(value, key) in experience">
          <el-form-item class="experience" :label="labels[key]">
            <el-input v-model="experience[key]" ></el-input>
          </el-form-item>
        </div>
      </el-form>
      <hr v-if="cancel">
      <i v-if="cancel" class="el-icon-circle-close" @click="removeExperience(index)"></i>
    </div>
    <el-button v-if="add" type="primary" @click="addExperience()">增加</el-button>
  </div>
</template>

<script>
  export default {
    name: 'Experiences',
    created: function () {
      this.addExperience();
    },
    props: {
      labels: {
        type: Object
      },
      title: {
        type: String
      },
      cancel: {
        type: Boolean
      },
      add: {
        type: Boolean
      },
      experiences: {
        type: Array,
        default: []
      }
    },
    methods: {
      addExperience(){
        let experience = {};
        for(let key in this.labels){
          experience[key] = '';
        }
        this.experiences.push(experience);
      },
      removeExperience(index){
        this.experiences.splice(index, 1)
      }
    }
  }
</script>

<style lang="scss" scoped>
  h2 {
    padding: 16px;
  }

  .experiences {
    position: relative;
  }

  .experiences > .el-icon-circle-close {
    position: absolute;
    right: 0;
    top: 0;
  }

  .experience {
    padding: 8px 32px;
  }
</style>
