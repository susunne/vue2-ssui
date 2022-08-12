<template>
    <div>
        <SSStep :stepInfo="stepInfo"></SSStep>
        <SSProcess :processInfo="processInfo"></SSProcess>
    </div>
</template>


<script>
export default {
    components: {  },
    data() {
        return {
            // 步骤条内容
            stepInfo: {
                list: [{
                    name: '步骤一'
                },
                {
                    name: '步骤二'
                },
                {
                    name: '步骤三'
                },
                ],
                //步骤条进度
                step: 2
            },
            processInfo: {
                list: [{
                    name: '步骤一'
                },
                {
                    name: '步骤二'
                },
                {
                    name: '步骤三'
                },
                {
                    name: '步骤四'
                },
                ],
                //步骤条进度
                step: 2
            }
        }
    }
}
</script>


<style lang="scss" scoped>
</style>