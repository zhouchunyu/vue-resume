<template>
  <div id="app">
    <Editor/>
    <Preview/>
    <Topbar/>
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
}
</style>
