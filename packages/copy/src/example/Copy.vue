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
import GrCopy from "../components/Copy";
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

<style lang="scss" scoped>
.test-view {
    box-sizing: border-box;
    padding: 20px;
}
.custom-label {
    color: pink;
    font-size: 14px;
    margin-left: 20px;
    padding: 5px;
    border: 1px solid pink;
    border-radius: 5px;
}
</style>
