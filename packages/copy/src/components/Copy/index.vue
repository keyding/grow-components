<template>
    <div
        class="copy-wrapper"
        :title="tooltip"
        v-clipboard:copy="copy"
        v-clipboard:success="handleCopy"
        v-clipboard:error="handleCopyError"
    >
        <slot>
            <div class="cont-wrapper" :class="{ disabled }">
                <span class="icon">
                    <svg
                        t="1608800326162"
                        viewBox="0 0 1024 1024"
                        version="1.1"
                        xmlns="http://www.w3.org/2000/svg"
                        p-id="4423"
                        width="20"
                        height="20"
                    >
                        <path
                            d="M146.212571 984.210286h448.219429a146.505143 146.505143 0 0 0 146.139429-146.505143v-76.580572h98.523428c68.754286 0 124.562286-55.881143 124.562286-124.562285v-491.52c0-68.681143-55.808-124.562286-124.562286-124.562286H347.648c-68.754286 0-124.562286 55.881143-124.562286 124.562286V243.565714H148.333714C66.56 243.565714 0 309.174857 0 389.851429v448.219428a146.285714 146.285714 0 0 0 146.212571 146.212572zM294.473143 145.042286c0-29.257143 23.844571-53.174857 53.174857-53.174857h491.52c29.257143 0 53.174857 23.917714 53.174857 53.174857v491.52c0 29.257143-23.917714 53.174857-53.248 53.174857H347.648a53.248 53.248 0 0 1-53.174857-53.174857v-491.52zM71.387429 389.851429c0-41.984 33.792-74.825143 76.946285-74.825143H223.085714v321.609143c0 68.754286 55.881143 124.562286 124.562286 124.562285H669.257143v76.580572c0 41.398857-33.572571 75.117714-74.825143 75.117714H146.212571a75.849143 75.849143 0 0 1-74.825142-74.825143V389.778286z"
                            p-id="4424"
                        />
                    </svg>
                </span>
                <span class="text">复制</span>
            </div>
        </slot>
    </div>
</template>

<script>
import clipboard from "./directives/clipboard";

/**
 * 复制
 * @prop { String} copy 需要复制的文本
 * @prop { String } tooltip 提示文字
 * @prop { Boolean } disabled 禁用
 * @emit { Function } success 复制成功后触发的方法
 * @emit { Function } error 复制失败后触发的方法
 */
export default {
    name: "KuCopy",
    directives: {
        clipboard,
    },
    props: {
        copy: {
            type: String,
            default: "",
        },
        tooltip: {
            type: String,
            default: "点击复制",
        },
        disabled: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        handleCopy() {
            !this.disabled && this.$emit("success", this.copy);
        },
        handleCopyError() {
            !this.disabled && this.$emit("error");
        },
    },
};
</script>

<style lang="scss" scoped>
$--copy-text-color-default: #322f4b;
$--copy-text-color-disable: #afafaf;

@mixin flex(
    $flex-direction: row,
    $align-items: center,
    $justify-content: center,
    $flex-wrap: nowrap
) {
    display: flex;
    flex-direction: $flex-direction;
    align-items: $align-items;
    justify-content: $justify-content;
    flex-wrap: $flex-wrap;
}

.copy-wrapper {
    display: inline-block;
    cursor: pointer;

    .cont-wrapper {
        @include flex(row, center, flex-start);

        color: $--copy-text-color-default;

        .icon {
            @include flex(row);
            fill: $--copy-text-color-default;
        }

        &.disabled {
            color: $--copy-text-color-disable;
            cursor: not-allowed;

            .icon {
                fill: $--copy-text-color-disable;
            }
        }

        .growiconfont {
            width: 16px;
            height: 16px;
        }

        .text {
            font-size: 14px;
            margin-left: 5px;
        }
    }
}
</style>
