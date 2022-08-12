<template>
    <div class="dialogView">
        <SSButton type="primary" @click="visible = true" class="dialogSwitch">显示对话框</SSButton>
        <SSDialog title="标题" width="40%" top="200px" :visible.sync="visible">
            这是内容
            <template v-slot:footer>
                <SSButton @click="visible = false">取消</SSButton>
                <SSButton type="primary" @click="visible = false">确定</SSButton>
            </template>
        </SSDialog>
    </div>
</template>


<script>
export default {
    data() {
        return {
            visible: false,
        }
    },
    components: {  },
}
</script>


<style lang="scss" scoped>
.dialogView {
    margin-top: 50px;
}
</style>