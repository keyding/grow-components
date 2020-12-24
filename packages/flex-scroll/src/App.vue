<template>
  <div id="app">
    <TestView></TestView>
  </div>
</template>

<script>
import TestView from "./example";
export default {
  name: "App",
  components: {
    TestView
  }
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
}

html,
body,
#app {
  width: 100%;
  height: 100%;
}
</style>
