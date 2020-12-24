<template>
  <div class="test-view">
    <VScroll></VScroll>
    <HScroll></HScroll>
  </div>
</template>

<script>
import VScroll from "./VScroll";
import HScroll from "./HScroll";
export default {
  name: "TestView",
  components: {
    VScroll,
    HScroll
  }
};
</script>

<style lang="scss" scoped>
.test-view {
  display: flex;
  width: 100%;
  height: 100%;
}
</style>
