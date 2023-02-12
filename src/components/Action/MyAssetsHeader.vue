<template>
    <header class="theMyAssetsHeader">
        <span class="theMyAssetsTitle">My assets</span>
        <div>
            <button @click="onClick" class="theMyAssetsOptions">
            {{chosed}}
                <img class="theMyAssetsDown" :src="down" alt="">    
            </button>
            <transition name="list">
                <div v-show="listFlag" class="theMyAssetsOptionsList">
                    <div v-for="option in options" :key="option">
                        <button @click="select(option)" class="theMyAssetsOptions">
                            {{option}}
                        </button>
                    </div>
                </div>
            </transition>
        </div>
    </header>
</template>

<script>
import {ref} from 'vue'
import down from '../../assets/icons/Action/more.svg'
export default {
    setup(){
        const options = ['Popular','New','Viewed']
        const listFlag = ref(false)
        let chosed = ref('Popular')
        const onClick = () => {
            listFlag.value = !listFlag.value
        }
        const select = (option) => {
            chosed.value = option
            listFlag.value = false
        }
        return{
            down,
            options,
            chosed,
            onClick,
            select,
            listFlag
        }
    }
}
</script>

<style scoped>
    .theMyAssetsHeader{
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: relative;
        margin-bottom: 25px;
    }
    .theMyAssetsTitle{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 24px;
        line-height: 29px;
        /* identical to box height */
        display: flex;
        align-items: center;

        color: #FFFFFF;
    }
    .theMyAssetsDown{
        width: 11px;
        height: 5.5px;
        margin-left: 0px;
    }
    .theMyAssetsOptions{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 12px 13.5px;
        background: #2d2d2d;
        height: 43px;
        width: 102px;
        border-radius: 8px;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #FFFFFF;
    }
    .theMyAssetsListButton{
    }
    .theMyAssetsOptionsList{
        position: absolute;
    }
    .theMyAssetsOptionsList .theMyAssetsOptions{    
        margin-top: 8px;
        justify-content: center;
    }
    .theMyAssetsOptionsList .theMyAssetsOptions:hover{    
        margin-top: 8px;
        justify-content: center;
        background: #404040;
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