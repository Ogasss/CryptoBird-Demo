<template>
    <div class="theConvertWrapper">
        <span class="theConvertTitle">Convert</span>
        
        <main class="theConvertMain">
            <ConvertInput/>
            <div class="exchange">
                <div class="line">
                </div>
                <img class="exchangeIcon" :src="exchange" alt="">
                <div class="line">
                </div>
            </div>
            <ConvertInput/>
            <div class="theConvertFooter">
                <span class="default">Transaction fee: 0.00$</span>
                <button class="theConvertButton">
                    Exchange
                </button>
            </div>
        </main>
    </div>
</template>

<script>
import exchange from '../../assets/icons/Action/exchange.svg'
import BTC from '../../assets/icons/Action/BTC.svg'
import USDT from '../../assets/icons/Action/USDT.svg'

import ConvertInput from './CovertInput.vue'

export default {
    components:{
        ConvertInput
    },
    setup(){
        return{
            exchange,
            BTC,
            USDT,
        }
    }
}
</script>

<style scoped>
    .theConvertWrapper{
        min-width: 480px;
    }
    .theConvertTitle{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 24px;
        align-items: center;
        color: #FFFFFF;
        
    }
    .theConvertMain{
        margin-top: 24px;
        background: #121212;
        height: 350px;
        border-radius: 16px;
        padding: 40px;
    }
    .exchange{
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 64px;
    }
    .line{
        border: 1px solid #343434;
        width: 40%;
        height: 1px;
    }
    .exchangeIcon{
        width: 32px;
        height: 32px;
        opacity: 0.4;
    }
    .exchangeIcon:hover{
        opacity: 1;
    }
    .theConvertFooter{
        margin-top: 24px;
        height: 54px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .default{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 19px;
        display: flex;
        align-items: center;
        color: #747474;
    }
    .theConvertButton{
        height: 54px;
        width: 124px;
        background: #1459f5;
        border-radius: 8px;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 18px;
        line-height: 22px;
        /* identical to box height */
        color: #FFFFFF;
        opacity: 1;
    }
    .theConvertButton:hover{
        background: linear-gradient(145deg, #3974fd, #002e9b);
    }
    .theConvertButton:active{
        opacity: 0.8;
    }
</style>