<template>
    <div id="app">
        <TestGrCopy></TestGrCopy>
    </div>
</template>

<script>
import TestGrCopy from "./example/Copy";
export default {
    name: "App",
    components: { TestGrCopy },
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
