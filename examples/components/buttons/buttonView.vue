<template>
    <div class="button-view">
        <div class="row">
            <SSButton @click="getInfo">按钮</SSButton>
            <SSButton type="primary" @click="getInfo">按钮</SSButton>
            <SSButton type="success" @click="getInfo">按钮</SSButton>
            <SSButton type="info" @click="getInfo">按钮</SSButton>
            <SSButton type="warning" @click="getInfo">按钮</SSButton>
            <SSButton type="danger" @click="getInfo">按钮</SSButton>
        </div>
        <div class="row">
            <SSButton plain>按钮</SSButton>
            <SSButton plain type="primary">按钮</SSButton>
            <SSButton plain type="success">按钮</SSButton>
            <SSButton plain type="info">按钮</SSButton>
            <SSButton plain type="warning">按钮</SSButton>
            <SSButton plain type="danger">按钮</SSButton>
        </div>
        <div class="row">
            <SSButton disabled>按钮</SSButton>
            <SSButton disabled>按钮</SSButton>
            <SSButton disabled>按钮</SSButton>
            <SSButton disabled>按钮</SSButton>
            <SSButton disabled>按钮</SSButton>
            <SSButton disabled>按钮</SSButton>
        </div>
    </div>
</template>


<script>
export default {
    components: {  },
    methods: {
        getInfo() {
            console.log('123')
        }
    }
}
</script>


<style lang="scss" scoped>
.button-view {
    .row {
        margin-top: 20px;
    }
}
</style>