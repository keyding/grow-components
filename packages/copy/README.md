# @grow-components/copy

## 安装

```
yarn add @grow-components/copy (npm i @grow-components/copy)
```

## 使用

```vue
<template>
  <div class="test-view">
    <!-- base -->
    <GrCopy
      copy="Copy components"
      tooltip="Click to copy"
      @success="handleSuccess"
      @err="handleError"
    ></GrCopy>

    <!-- disabled -->
    <GrCopy
      copy="Copy components"
      tooltip="Click to copy"
      disabled
      @success="handleSuccess"
      @err="handleError"
    ></GrCopy>

    <!-- slot -->
    <GrCopy
      copy="Copy components"
      tooltip="Click to copy"
      disabled
      @success="handleSuccess"
      @err="handleError"
    >
      <span class="custom-label">点我复制</span>
    </GrCopy>
  </div>
</template>

<script>
import GrCopy from "@grow-components/copy";
export default {
  name: "TestGrCopy",
  components: { GrCopy },
  methods: {
    handleSuccess() {
      console.log("copy success");
    },
    handleError() {
      console.log("copy error");
    },
  },
};
</script>
```
