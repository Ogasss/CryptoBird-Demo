<template>
<div class="theConvertInputWrapper">
    <div class="theConvertInput">
        <input type="number" placeholder="Please input">
        <button @click="onClick" class="theConvertListButton">
            <img class="convertIcon" :src="chosedOption[0]">
            <span>{{chosedOption[1]}}</span>
            <img class="down" :src="down" alt="">
        </button>
    </div>

    <transition name="list">
        <div v-show="listFlag" class="theConvertList">
            <div v-for="option in options" :key="option[1]">
                <button @click="select(option[0],option[1])" class="theConvertListButton">
                    <img class="convertIcon" :src="option[0]">
                    <span>{{option[1]}}</span>
                </button>
            </div>
        </div>
    </transition>
    
    
</div>
</template>
<script>
import {ref} from 'vue'
import down from '../../assets/icons/Action/more.svg'
import BTC from '../../assets/icons/Action/BTC.svg'
import USDT from '../../assets/icons/Action/USDT.svg'
import ETH from '../../assets/icons/Action/ETH.svg'
import LTE from '../../assets/icons/Action/LTE.svg'
import DOGE from '../../assets/icons/Action/DOGE.svg'

export default {
    setup(){
        let listFlag = ref(false)
        let chosedOption = [BTC,'BTC']
        const onClick = () => {
            listFlag.value = !listFlag.value
        }
        const select = (svg,text) => {
            chosedOption[0] = svg
            chosedOption[1] = text
            listFlag.value = false
        }
        const options = [
            [BTC,'BTC'],
            [USDT,'USDT'],
            [ETH,'ETH'],
            [LTE,'LTE'],
            [DOGE,'DOGE'],
        ]
        return {
            down,
            options,
            listFlag,
            onClick,
            select,
            chosedOption
        }
    }    
}
</script>
<style scoped>
    .theConvertInput{
        height: 64px;
        border-radius: 8px;
        background: #343434;
        display: flex;
        align-items: center;
    }
    .theConvertInput > input{
        width: 60%;
        height: 100%;
        margin-left: 16px;
        color: #FFFFFF;
    }
    .theConvertInput > input:focus{
        width: 60%;
        height: 100%;
        margin-left: 16px;
        color: #FFFFFF;
    }
    .theConvertListButton{
        position: relative;
        margin-left: 16px;
        height: 48px;
        width: 117px;
        border-radius: 8px;
        background: #404040;
        display: flex;
        align-items: center;
    }
    .convertIcon{
        width: 24px;
        height: 24px;
        margin-left: 14px;
    }
    .down{
        margin-left: 8px;
        width: 11px;
        height: 5.5px;
    }
    .theConvertListButton span{
        margin-left: 16px;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;

        color: #FFFFFF;
    }

    .theConvertInputWrapper{
        position: relative;
        display: flex;
        flex-direction: column;
    }
    .theConvertList{
        position: absolute;
        height: 110px;
        overflow: auto;
        display: flex;
        flex-direction: column;
        top: 100%;
        left: 272.5px;
        z-index: 2;
    }
    .theConvertList::-webkit-scrollbar{
        display: none;
    }
    .theConvertList .theConvertListButton{
        margin-left: 0px;
        margin-bottom: 8px;
    }
    .theConvertList .theConvertListButton:hover{
        margin-left: 0px;
        margin-bottom: 8px;
        background: linear-gradient(145deg, #949494, #6b6b6b);
    }

    .list-enter-from,
    .list-leave-to{
        transform: translateY(-50px);
        opacity: 0;
    }
    .list-enter-to,
    .list-leave-from{
        transform: translateY(0px);
        opacity: 1;
    }
    .list-enter-active,
    .list-leave-active{
        transition: all 0.3s ease;
    }
</style>