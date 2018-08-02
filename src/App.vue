<template>
  <div id="app">
    <div class="topbar">
      <Topbar/>
    </div>
    <main>
      <Editor class="editor"/>
      <Preview class="preview"/>
    </main>
  </div>
</template>

<script>
import Editor from "./components/Editor";
import Preview from "./components/Preview";
import Topbar from "./components/Topbar";

export default {
  name: 'App',
  components: {
    Editor,
    Preview,
    Topbar
  }
}
</script>

<style>
#app {
  font-family: -apple-system, "Noto Sans", "Helvetica Neue", Helvetica, "Nimbus Sans L", Arial, "Liberation Sans", "PingFang SC", "Hiragino Sans GB", "Noto Sans CJK SC", "Source Han Sans SC", "Source Han Sans CN", "Microsoft YaHei", "Wenquanyi Micro Hei", "WenQuanYi Zen Hei", "ST Heiti", SimHei, "WenQuanYi Zen Hei Sharp", sans-serif;
  height: 100vh;
  display: flex;
  flex-direction: column;
}
main {
  flex: 1;
  display: flex;
  justify-content: space-between;
}

.topbar{
  height: 10em;
  background-color: red;
}

.editor{
  width: 20em;
  background-color: green;
}
.preview{
  flex: 1;
  background-color: blue;
}
</style>
