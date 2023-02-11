<template>
    <div class="theActionWrapper">
        <div class="header">
            <Header/>
        </div>

        <div class="convert">
            <Convert/>
        </div>

        <div class="myAssets">
            <MyAssets/>
        </div>
    </div>
</template>

<script>
import Header from './Header.vue'
import Convert from './Convert.vue'
import MyAssets from './MyAssets.vue'
export default {
    components:{
        Header,
        Convert,
        MyAssets
    }
}
</script>

<style scoped>
    .theActionWrapper{
        min-width: 400px;
        width: 100%;
        height: 100%;
        background: #1A1A1A;
        padding: 40px 64px;
    }
    .theActionWrapper > .header{
        margin-bottom: 6%;
    }
    .theActionWrapper > .convert{
        margin-bottom: 3.7%;
    }
    .theActionWrapper > .myAssets{
        width: 100%;
        height: calc(52.16% + 43px);
    }
    @media (max-height: 980px){
        .theActionWrapper > .myAssets{
            width: 100%;
            height: 42.16%;
        }
    }
    @media (max-width: 1720px){
        .convert{
            display: none;
        }
        .theActionWrapper > .myAssets{
            height: 100%;
            width: 100%;
        }
    }
</style>