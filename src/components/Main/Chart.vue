<template>
    <div class="chartWrapper">
        <div id="chart" class="chart"></div>
        <!-- <div id="chart1" class="chart"> 
        </div>
        <div id="chart2" class="chart">  
        </div> -->
        <div class="xAxis">
            <div v-for="item in dateItems" :key="item">
                <span>{{item}}</span>
            </div>
        </div>
    </div>
</template>

<script>
import * as echarts from 'echarts'
import { ref } from 'vue'
import { computed, onMounted, watch } from 'vue'
export default {
    props:[
        'date',
        'trend'
    ],
    setup(props){
        var myChart
        const daily = ['1','2','3','4','5','6','7','8']
        const monthly = ['July','August','September']
        const yearly = ['2021','2022','2023']
        const date = computed(()=>{
            return props.date
        })
        const trend = computed(()=>{
            return props.trend
        })
        const dateItems = computed(()=>{
            if(date.value === 'Daily'){
                return daily
            }
            if(date.value === 'Monthly'){
                return monthly
            }
            if(date.value === 'Yearly'){
                return yearly
            }
        })
        let screenWidth = ref(document.body.clientWidth)
        let screenHeight = ref(document.body.clientHeight)
        var timeout = null
        watch(screenWidth,()=>{
            if(timeout !== null) {clearTimeout(timeout)}
            timeout = setTimeout(()=>{
                myChart = loadChart(myChart)
            }, 300)
        })
        watch(screenHeight,()=>{
            if(timeout !== null) {clearTimeout(timeout)}
            timeout = setTimeout(()=>{
                myChart = loadChart(myChart)
            }, 300)
        })
        watch(date, () => {
            initChart(myChart)
        })
        watch(trend, ()=>{
            initChart(myChart)
        })
        const loadChart = (myChart) => {
            myChart.dispose()
            let newChart = echarts.init(document.getElementById('chart'))
            initChart(newChart)
            return newChart
        }
        const initChart = (myChart)=>{
            let XData = []
            let YData = []
            const fake = (max,min) => {
                for(let i =0 ;i<31;i++){
                    const j = Math.random()*(max-min)+min
                    YData.push(j)
                    XData.push(' ')
                }
            }
            fake(1680000,1700000)
            fake(1720000,1730000)
            fake(1720000,1740000)
            fake(1720000,1730000)
            fake(1730000,1740000)
            fake(1740000,1760000)
            fake(1740000,1760000)
            fake(1760000,1780000)
            myChart.setOption({
                grid: {
                    top: '8px',
                    bottom: '8px',
                    left: '64px',
                    right: '2px',
                },
                xAxis: {
                    type: 'category',
                    data: XData,
                    show: false,
                },
                yAxis: {
                    splitLine:{
                        lineStyle:{
                            type: 'dashed',
                            color: '#292929',
                        },
                        show: true
                    },
                    type: 'value',
                    min: 1680000,
                },
                series: [
                    {
                        data: YData,
                        type: 'line',
                        symbol: 'none',
                        itemStyle:{
                            color: "#1459F5"
                        },
                        areaStyle:{
                            normal:{
                                color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                                {
                                    offset: 0,
                                    color: 'rgb(20, 89, 245, 0.3)', // 0% 处的颜色
                                },
                                {
                                    offset: 1,
                                    color: "#101010", // 100% 处的颜色
                                },
                                ]),
                            }
                        },
                        label: {
                            normal: {
                                formData: '11'
                            }
                        }
                    }
                ]
            })
        }
        onMounted(()=>{
            myChart = echarts.init(document.getElementById('chart'))
            initChart(myChart)
            window.onresize = () => {
                return (() => {
                    screenWidth.value = document.body.clientWidth
                    screenHeight.value = document.body.clientHeight
                })()
            }
        })
        return{
            dateItems
        }
    },
}
</script>

<style scoped>
    .chartWrapper{
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .chart{
        width: 100%;
        height: 80%;
    }
    .xAxis{
        width: 80%;
        display: flex;
        justify-content: space-between;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #747474;
    }
</style>