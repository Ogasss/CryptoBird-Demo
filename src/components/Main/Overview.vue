<template>
    <div class="theOverviewWrapper">
        <div class="title">Trend Overview</div>
        <div class="options">
            <div class="listWrapper">
                <button @click="trendOptionsClick" class="listButton">
                    {{trend}}
                    <img :src="more" alt="">
                </button>
                <transition name="list">
                    <div v-show="trendOptionsFlag" class="list">
                        <div v-for="option in trendOptions" :key="option">
                            <button @click="trendSelect(option)" class="listButton listButtonOption">
                                {{option}}
                            </button>
                        </div>
                    </div>
                </transition>
            </div>

            <div class="date">
                <div v-for="option in dateOptions" :key="option" >
                    <button @click="selectDate(option)" :class="date === option?'dateButton active' : 'dateButton'">{{option}}</button>
                </div>
            </div>

        </div>
        <div class="overviewWrapper">
            <Chart :date="date" :trend="trend"/>
        </div>
    </div>
</template>

<script>
import {ref} from 'vue'
import more from '../../assets/icons/Action/more.svg'
import Chart from './Chart.vue'
export default {
    components:{
        Chart
    },
    setup(){
        const trend  = ref('BTC')
        const trendOptions = ['BTC','ETH','LTE','DOGE']
        const trendOptionsFlag = ref(false)
        const trendOptionsClick = () => {
            trendOptionsFlag.value = !trendOptionsFlag.value
        }
        const trendSelect = (option) => {
            trend.value = option
            trendOptionsFlag.value = false
        }

        
        const date = ref('Monthly')
        const dateOptions = ['Daily','Monthly','Yearly']
        const selectDate = (option) => {
            date.value = option
        }
        return {
            more,
            trend,
            trendOptions,
            date,
            dateOptions,
            selectDate,
            trendOptionsFlag,
            trendOptionsClick,
            trendSelect
        }
    }
}
</script>

<style scoped>
    .theOverviewWrapper{
        width: 100%;
        height: 55.55%;
        padding: 36px 64px;
        display: flex;
        flex-direction: column;
    }
    .theOverviewWrapper .overviewWrapper{
        height: 70%;
        width: 100%;
        overflow: hidden;
    }
    .theOverviewWrapper .title{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 24px;
        line-height: 29px;
        color: #FFFFFF;
    }
    .theOverviewWrapper .title{
        margin-bottom: auto;
    }
    .theOverviewWrapper .options{
        display: flex;
        justify-content: space-between;
        margin-bottom: auto;
    }
    .theOverviewWrapper .options .listWrapper{
        position: relative;
    }
    .theOverviewWrapper .options .listWrapper .listButton{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #FFFFFF;
        width: 81px;
        height: 43px;
        background: #343434;
        border-radius: 8px;
    }
    .options .listWrapper .list {
        position: absolute;
        height: 128px;
        overflow: auto;
        z-index: 2;
    }
    .options .listWrapper .list::-webkit-scrollbar{
        display: none;
    }
    .listWrapper .list .listButtonOption{
        margin-top: 8px;
    }
    .listWrapper .list .listButtonOption:hover{
        margin-top: 8px;
        background: #404040;
    }
    .theOverviewWrapper .options .date{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .theOverviewWrapper .options .date .dateButton{
        width: 91px;
        height: 35px;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #747474;
        margin-left: 14px;
        transition: 0.3s all ease;
    }
    .theOverviewWrapper .options .date .active{
        color: #fff;
        background: #343434;
        border-radius: 24px;
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