<template>
    <div class="AssetWrapper">
        <header class="AssetHeader">
            <img :src="icon" alt="">
            <div class="AssetText">
                <span class="title">{{name}}</span>
                <span class="simpleName">{{simple}}</span>
            </div>
        </header>

        <main class="AssetMain">
            <img :src="trendImage" alt="">
        </main>

        <footer class="AssetFooter">
            <span class="price">{{price}}</span>
            <button class="trend">
                <span class="trendText">
                    {{trendType}}{{trend}}%
                </span>
                <img class="trendIcon" :src="up" alt="">                    
            </button>
        </footer>
    </div>
</template>

<script>
import up from '../../assets/icons/Action/Up.svg'

export default {
    props:[
        "name",
        "simple",
        "price",
        "trendType",
        "trend",
        "icon",
        "trendImage"
    ],
    setup(){
        return{
            up
        }
    }
}
</script>

<style scoped>
    .AssetWrapper{
        display: flex;
        flex-direction: column;
        padding: 24px;
        background: #121212;
        border-radius: 16px;
    }
    .AssetWrapper:hover{
        background: #333;
    }
    .AssetWrapper header img{
        width: 48px;
        height: 48px;
    }
    .AssetWrapper .AssetHeader{
        display: flex;
    }
   .AssetHeader .AssetText{
        margin-left: 24px;
        display: flex;
        flex-direction: column;
    }
   .AssetHeader .title{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 20px;
        line-height: 24px;
        color: #FFFFFF;
        margin-bottom: 4px;
    }
    .AssetHeader .simpleName{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 17px;
        line-height: 20px;
        color: #747474;
    }
    .AssetWrapper .AssetFooter{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .AssetFooter .price{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 18px;
        line-height: 22px;
        color: #FFFFFF;
    }
    .AssetFooter .trend{
        width: 73px;
        height: 30px;
        border-radius: 32px;
        background: rgba(46, 190, 123, 0.2);
    }
    .trend .trendText{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #2EBE7B;
    }
    .AssetFooter .down{

    }
    .AssetFooter .up{

    }
    .AssetWrapper .AssetMain{
        margin-top: 16px;
        margin-bottom: 16px;
        width: 180px;
        height: 60px;
        margin: auto;
    }
</style>