<template>
  <div id="app">
    <header>
      <Topbar class="topbar" :class="{previewMode: previewMode}" @preview="toggle_preview()" />
    </header>
    <main>
      <Editor class="editor" :class="{previewMode: previewMode}" :resume="resume" />
      <Preview class="preview" :class="{previewMode: previewMode}" :resume="resume" @preview="toggle_preview()" />
    </main>
  </div>
</template>

<script>
import Editor from "./components/Editor";
import Preview from "./components/Preview";
import Topbar from "./components/Topbar";

export default {
  name: 'App',
  data(){
    return {
      resume: {
        profileInfo: [],
        workingExp: [],
        learningExp: [],
        projectsExp: [],
        contactInfo: []
      },
      previewMode: false
    }
  },
  components: {
    Editor,
    Preview,
    Topbar
  },
  methods: {
    toggle_preview() {
      this.previewMode = !this.previewMode;
    }
}

}
</script>

<style lang="scss">
#app {
  font-family: -apple-system, "Noto Sans", "Helvetica Neue", Helvetica, "Nimbus Sans L", Arial, "Liberation Sans", "PingFang SC", "Hiragino Sans GB", "Noto Sans CJK SC", "Source Han Sans SC", "Source Han Sans CN", "Microsoft YaHei", "Wenquanyi Micro Hei", "WenQuanYi Zen Hei", "ST Heiti", SimHei, "WenQuanYi Zen Hei Sharp", sans-serif;
  height: 100vh;
  display: flex;
  flex-direction: column;
}
.topbar {
  height: 4em;
  /*background-color: red;*/
  background-color: #FFFFFF;
  position: relative;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 20px;
  padding: 16px;

  &.previewMode {
    display: none;
  }
}

main {
  flex: 1;
  display: flex;
  background: white;
  justify-content: space-between;
}

.preview{
  flex: 1;
  margin: 16px 16px 16px 8px;
  background-color: white;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.5);
  border-radius: 4px;
  &.previewMode {
    max-width: 960px;
    margin-left: auto;
    margin-right: auto;
  }
}

</style>
