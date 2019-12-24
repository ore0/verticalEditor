<template>
  <div id="app">
    <VerticalEditor />
  </div>
</template>

<script>
import VerticalEditor from "./components/VerticalEditor.vue";

export default {
  name: "app",
  components: {
    VerticalEditor
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Noto+Serif+JP:400,700&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
