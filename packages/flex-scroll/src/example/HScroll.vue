<template>
  <div class="h-scroll-view">
    <div class="header">HScroll</div>
    <div class="content">
      <flex-scroll scroll="x">
        <div class="list">
          <div class="item" v-for="n in 50" :key="n">{{ n }}</div>
        </div>
      </flex-scroll>
    </div>
  </div>
</template>

<script>
import FlexScroll from "../../lib/flex-scroll.umd";

export default {
  name: "HScroll",
  components: {
    FlexScroll
  }
};
</script>

<style scoped>
.h-scroll-view {
  display: flex;
  flex-direction: row;
  width: 800px;
  height: 100%;
}

.header {
  width: 100px;
  height: 100px;
  line-height: 100px;
  background: pink;
  text-align: center;
}

.content {
  flex: 1;
  overflow: auto;
}

.list {
  display: flex;
  flex-direction: row;
}

.item {
  width: 36px;
  height: 100px;
  line-height: 100px;
  border-right: 1px solid #ccc;
  text-align: center;
  flex-shrink: 0;
}
</style>
