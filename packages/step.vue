<template>
    <div class="step">
        <ul style="list-style: none; display: flex;">
            <li class="stepItem" v-for="(stepItem, index) in stepInfo.list" :key="index">
                <!-- 模拟步骤条的节点，此处为圆圈 -->
                <div :class="stepInfo.step >= index + 1 ? 'icon active' : 'icon'"></div>
                <!-- 模拟步骤条连接线，动态显示  -->
                <div :class="stepInfo.step >= index + 2 ? 'line lineActive' : 'line'"
                    v-show="index !== stepInfo.list.length - 1"></div>
                <!-- 步骤名称  -->
                <div :class="stepInfo.step >= index + 1 ? 'stepStatus' : 'stepStatus2'">{{ stepItem.name }}</div>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    name: 'SSStep',
    props: {
        stepInfo: {
            type: Object,
            default: function () {
                return {
                    list: [],
                    step: 0
                }
            }
        }
    }
}
</script>


<style lang="scss" scoped>
.step {
    margin-top: 50px;
    width: 100%;
    display: flex;
    justify-content: space-between;
}

/* 两点间间距 */
.stepItem {
    width: 200px;
    height: 70px;
    float: left;
    font-size: 14px;
    position: relative;
    font-family: PingFangSC-Medium;
}

.icon {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: rgba(217, 217, 217, 1);
    position: relative;
    z-index: 888;
}

.active {
    background-color: #337DFF;
}

/* 线条 */
.line {
    position: absolute;
    top: 15px;
    left: 40px;
    border-bottom: 1px solid rgba(217, 217, 217, 1);
    width: 150px;
    z-index: 111;
}

.lineActive {
    border-bottom: 1px solid rgba(51, 125, 255, 1);
}

/* 下面字体颜色 */
.stepStatus {
    color: #333333;
    line-height: 36px;
    margin-top: 5px;
}

.stepStatus2 {
    color: #999999;
    line-height: 36px;
    margin-top: 5px;
}
</style>