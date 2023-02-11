<template>
    <div class="AssetsMainWrapper">
        <Asset
            v-for="asset in arr" :key="asset.name"
            class="asset"
            :name = "asset.name"
            :simple= "asset.simple"
            :price = "asset.price"
            :trendType = "asset.trendType"
            :trend = "asset.trend"
            :icon = "asset.icon"
            :trendImage = "asset.trendImage"
        />
    </div>
</template>

<script>
import Asset from './Asset.vue'

import BTCSrc from '../../assets/icons/Action/BTC.svg'
import BTCTrend from '../../assets/icons/Action/BTCofTrend.svg'
import ETHSrc from '../../assets/icons/Action/ETH.svg'
import ETHofTrend from '../../assets/icons/Action/ETHofTrend.svg'
import LTESrc from '../../assets/icons/Action/LTE.svg'
import LTEofTrend from '../../assets/icons/Action/LTEofTrend.svg'
import DOGESrc from '../../assets/icons/Action/DOGE.svg'
import DOGEofTrend from '../../assets/icons/Action/DOGEofTrend.svg'


export default {
    
    components:{
        Asset
    },
    setup(){
        const arr = [
            {
                name: 'Bitcoin',
                simple: 'BTC',
                price: '$17.780,16',
                trendType: '+',
                trend: '1,2',
                icon: BTCSrc,
                trendImage: BTCTrend
            },
            {
                name: 'Ethereum',
                simple: 'ETH',
                price: '$17.780,16',
                trendType: '-',
                trend: '1,2',
                icon: ETHSrc,
                trendImage: ETHofTrend
            },
            {
                name: 'Litecoin',
                simple: 'LTE',
                price: '$17.780,16',
                trendType: '+',
                trend: '1,2',
                icon: LTESrc,
                trendImage: LTEofTrend
            },
            {
                name: 'Doge Coin',
                simple: 'DOGE',
                price: '$17.780,16',
                trendType: '-',
                trend: '1,2',
                icon: DOGESrc,
                trendImage: DOGEofTrend
            },
        ]
        return {
            arr
        }
    }
}
</script>

<style scoped>
    .AssetsMainWrapper{
        width: 100%;
        height: 88.5%;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
    .AssetsMainWrapper::-webkit-scrollbar{
        display: none;
    }
    .AssetsMainWrapper .asset{
        height: 218px;
        margin-bottom: 24px;
    }
    @media (max-width: 1845px){
        .AssetsMainWrapper{
            overflow: auto;
        }
        .asset{
            width: 100%
        }
    }
</style>