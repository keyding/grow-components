<template>
  <div
    class="flex-scroll--view"
    :class="{ vertical: scrollY, horizontal: scrollX }"
  >
    <div class="flex-scroll--wrapper">
      <div class="flex-scroll--content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
/**
 * FlexScroll - 滚动容器
 *
 * flex 布局项目的自适应滚动
 */
export default {
  name: "FlexScroll",
  props: {
    scroll: {
      type: String,
      default: "y",
      validator(val) {
        return ["x", "y"].includes(val);
      }
    }
  },
  computed: {
    scrollX() {
      return this.scroll === "x";
    },
    scrollY() {
      return this.scroll === "y";
    }
  }
};
</script>

<style lang="scss" scoped>
@mixin flex($flex-direction: row) {
  display: flex;
  flex-direction: $flex-direction;
  align-items: flex-start;
  justify-content: flex-start;
  flex-wrap: nowrap;
}
.flex-scroll--view {
  width: 100%;
  height: 100%;

  .flex-scroll--wrapper {
    flex: 1;
    .flex-scroll--content {
      box-sizing: border-box;
      overflow: auto;
    }
  }

  &.horizontal {
    @include flex(row);

    .flex-scroll--wrapper {
      width: 0;

      .flex-scroll--content {
        max-width: 100%;
      }
    }
  }

  &.vertical {
    @include flex(column);

    .flex-scroll--wrapper {
      width: 100%;
      height: 0;

      .flex-scroll--content {
        max-height: 100%;
      }
    }
  }
}
</style>
