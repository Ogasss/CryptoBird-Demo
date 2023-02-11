<template>
    <div class="AssetsMainWrapper">
        <Asset class="asset"/>
        <Asset class="asset"/>
        <Asset class="asset"/>
        <Asset class="asset"/>
    </div>
</template>

<script>
import Asset from './Asset.vue'
export default {
    components:{
        Asset
    },
    setup(){
        
    }
}
</script>

<style scoped>
    .AssetsMainWrapper{
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
    .AssetsMainWrapper .asset{
        width: 228px;
        height: 218px;
        margin-bottom: 24px;
    }
    @media (max-width: 1845px){
        .AssetsMainWrapper .asset{
        width: 100%;
        height: 218px;
        margin-bottom: 24px;
    }
    }
</style>