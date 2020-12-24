# @grow-components/flex-scroll

`flex` 布局中项目的自适应滚动组件。

## 安装

```
yarn add @grow-components/flex-scroll (npm i @grow-components/flex-scroll)
```

### 使用

`VScroll.vue`

```js
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
import FlexScroll from "@grow-components/flex-scroll";

export default {
    name: "VScroll",
    components: {
        FlexScroll,
    },
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

```

`HScroll.vue`

```js
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
import FlexScroll from "@grow-components/flex-scroll";

export default {
    name: "HScroll",
    components: {
        FlexScroll,
    },
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

```
