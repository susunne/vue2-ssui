<template>
    <div class="process">
        <ul style="list-style: none; display: flex;">
            <li class="processItem" v-for="(processItem, index) in processInfo.list" :key="index">
                <!-- 模拟步骤条的节点，此处为圆圈 -->
                <span class="icon past" v-if="index + 1 < processInfo.step">
                    <!-- {{ index + 1 }} -->
                    <svg class="svg" t="1660281867572" viewBox="0 0 1466 1024" version="1.1"
                        xmlns="http://www.w3.org/2000/svg" p-id="1303" width="15" height="11">
                        <path
                            d="M535.770344 1017.621782c-51.025747 0-102.051494-19.134655-140.320804-63.782184L19.134655 539.255403C-6.378218 513.742529 0 475.473219 25.512874 449.960345s63.782184-19.134655 89.295057 6.378219l376.314885 414.584195c25.512874 25.512874 63.782184 25.512874 89.295057 6.378218l6.378218-6.378218L1326.669424 22.619714c25.512874-25.512874 63.782184-31.891092 89.295057-6.378219 25.512874 25.512874 31.891092 63.782184 6.378219 89.295058L676.091149 953.839598l-12.756437 12.756437c-38.26931 31.891092-82.916839 51.025747-127.564368 51.025747z"
                            p-id="1304"></path>
                    </svg>
                </span>
                <span class="icon active" v-else-if="index + 1 === processInfo.step">
                    {{ index + 1 }}
                </span>
                <span class="icon" v-else>
                    {{ index + 1 }}
                </span>
                <!-- 模拟步骤条连接线，动态显示  -->
                <div :class="processInfo.step >= index + 2 ? 'line lineActive' : 'line'"
                    v-show="index !== processInfo.list.length - 1"></div>
                <!-- 步骤名称  -->
                <div :class="processInfo.step >= index + 1 ? 'processStatus' : 'processStatus2'">{{ processItem.name }}
                </div>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    name: 'SSProcess',
    props: {
        processInfo: {
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
.process {
    margin-top: 50px;
    width: 100%;
    height: 100px;
    display: flex;
    justify-content: space-between;
}

/* 两点间间距 */
.processItem {
    width: 200px;
    height: 70px;
    float: left;
    font-size: 14px;
    position: relative;
    font-family: PingFangSC-Medium;
}

.icon {
    display: inline-block;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: #ffffff;
    border: 1.5px solid rgba(217, 217, 217, 1);
    position: relative;
    z-index: 888;
    text-align: center;
    line-height: 30px;
    font-family: PingFangSC-Regular;
    color: #999999;
}

.active {
    background-color: #337DFF;
    border: 1.5px solid #337dff;
    color: #FFFFFF;
}

.past {
    border: 1.5px solid #337dff;

    .svg {
        fill: #337DFF;
    }
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
.processStatus {
    color: #333333;
    line-height: 36px;
    margin-top: 5px;
}

.processStatus2 {
    color: #999999;
    line-height: 36px;
    margin-top: 5px;
}
</style>