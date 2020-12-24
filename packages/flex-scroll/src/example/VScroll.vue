<template>
  <div class="v-scroll-view">
    <div class="header">VScroll</div>
    <div class="content">
      <flex-scroll>
        <div class="item" v-for="n in 50" :key="n">{{ n }}</div>
      </flex-scroll>
    </div>
  </div>
</template>

<script>
import FlexScroll from "../../lib/flex-scroll.umd";

export default {
  name: "VScroll",
  components: {
    FlexScroll
  }
};
</script>

<style scoped>
.v-scroll-view {
  display: flex;
  flex-direction: column;
  width: 400px;
  height: 100%;
}

.header {
  height: 40px;
  line-height: 40px;
  background: pink;
  text-align: center;
}

.content {
  flex: 1;
}

.item {
  height: 36px;
  line-height: 36px;
  border-bottom: 1px solid #ccc;
  text-align: center;
}
</style>
