<template>
    <button class="s-button" :class="[`s-button-${type}`, {
        'is-plain': plain,
        'is-disabled': disabled
    }]" :disabled="disabled" @click="handleClick"><span>
            <slot></slot>
        </span></button>
</template>


<script>
export default {
    name: 'SSButton',
    props: {
        type: {
            type: String,
            default: 'default',
        },
        plain: {
            type: Boolean,
            default: false,
        },
        disabled: {
            type: Boolean,
            default: false,
        }
    },
    methods: {
        handleClick(e) {
            this.$emit('click', e)
        }
    }
}
</script>


<style lang="scss" scoped>
.s-button {
    display: inline-block;
    line-height: 1;
    white-space: nowrap;
    cursor: pointer;
    background: #ffffff;
    border: 1px solid #dcdfe6;
    color: #606266;
    -webkit-appearance: none;
    text-align: center;
    box-sizing: border-box;
    outline: none;
    margin: 0;
    transition: 0.1s;
    font-weight: 500;
    //禁止元素的文字被选中
    -moz-user-select: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    padding: 12px 20px;
    font-size: 14px;
    border-radius: 2px;
    margin-left: 20px;
    font-family: PingFangSC-Regular;

    &:hover,
    &:hover {
        color: #409eff;
        border-color: #c6e2ff;
        background-color: #ecf5ff;
    }
}

.s-button-primary {
    color: #fff;
    background-color: #409eff;
    border-color: #409eff;

    &:hover,
    &:focus {
        background: #66b1ff;
        background-color: #66b1ff;
        color: #fff;
    }
}

.s-button-success {
    color: #fff;
    background-color: #67c23a;
    border-color: #67c23a;

    &:hover,
    &:focus {
        background: #85ce61;
        background-color: #85ce61;
        color: #fff;
    }
}

.s-button-info {
    color: #fff;
    background-color: #909399;
    border-color: #909399;

    &:hover,
    &:focus {
        background: #a6a9ad;
        background-color: #a6a9ad;
        color: #fff;
    }
}

.s-button-warning {
    color: #fff;
    background-color: #e6a23c;
    border-color: #e6a23c;

    &:hover,
    &:focus {
        background: #ebb563;
        background-color: #ebb563;
        color: #fff;
    }
}

.s-button-danger {
    color: #fff;
    background-color: #f56c6c;
    border-color: #f56c6c;

    &:hover,
    &:focus {
        background: #f78989;
        background-color: #f78989;
        color: #fff;
    }
}

// 朴素按钮样式
.s-button.is-plain {

    &:hover,
    &:focus {
        background: #fff;
        border-color: #489eff;
        color: #409eff;
    }
}

.s-button-primary.is-plain {
    color: #409eff;
    background: #ecf5ff;

    &:hover,
    &:focus {
        background: #409eff;
        border-color: #409eff;
        color: #fff;
    }
}

.s-button-success.is-plain {
    color: #67c23a;
    background: #c2e7b0;

    &:hover,
    &:focus {
        background: #67c23a;
        border-color: #67c23a;
        color: #fff;
    }
}

.s-button-info.is-plain {
    color: #909399;
    background: #d3d4d6;

    &:hover,
    &:focus {
        background: #909399;
        border-color: #909399;
        color: #fff;
    }
}

.s-button-warning.is-plain {
    color: #e6a23c;
    background: #f5dab1;

    &:hover,
    &:focus {
        background: #e6a23c;
        border-color: #e6a23c;
        color: #fff;
    }
}

.s-button-danger.is-plain {
    color: #f56c6c;
    background: #fbc4c4;

    &:hover,
    &:focus {
        background: #f56c6c;
        border-color: #f56c6c;
        color: #fff;
    }
}

.s-button.is-disabled {
    cursor: no-drop;
    color: #c4c5c7;
    background: #f3f5f9;
}
</style>