<template>
    <div class="theDashBoardWrapper">
        <header>
            <span class="title">Dashboard</span>
            <button class="manage">
                Manage
                <img class="manageIcon" :src="manage" alt="">    
            </button>
        </header>

        <main>
            <span class="title">Total Balance</span>
            <div class="balance">
                <span class="balanceNumber">$62,340.48</span>
                <div class="trend">
                    <span class="trendText">+1,2%</span>
                    <img :src="up" alt="">
                </div>
            </div>
        </main>

        <footer>
            <div class="date">
                <div class="item">
                    <span class="text">Today</span>
                    <div>
                        <span>+1,2%</span>
                        <img :src="up" alt="">
                    </div>
                </div>
                <div class="line"></div>
                <div class="item">
                    <span class="text">7 Days</span>
                    <div>
                        <span>+4,3%</span>
                        <img :src="up" alt="">
                    </div>
                </div>
                <div class="line"></div>
                <div class="item">
                    <span class="text">30 Days</span>
                    <div>
                        <span>-11,8%</span>
                        <img :src="down" alt="">
                    </div>
                </div>
            </div>
            <div class="buttons">
                <button class="add">
                    <img :src="Add" alt="">
                    <span>Add</span>
                </button>
                <button class="withdraw">
                    <img :src="Withdraw" alt="">
                    <span>Withdraw</span>
                </button>
                <button class="convert">
                    <img :src="Convert" alt="">
                    <span>Convert</span>
                </button>
            </div>
        </footer>
    </div>
</template>

<script>
import manage from '../../assets/icons/Main/manage.svg'
import up from '../../assets/icons/Action/Up.svg'
import down from '../../assets/icons/Action/Down.svg'
import Add from '../../assets/icons/Main/Add.svg'
import Withdraw from '../../assets/icons/Main/Withdraw.svg'
import Convert from '../../assets/icons/Main/Convert.svg'

export default {
    setup(){
        return {
            manage,
            up,
            Add,
            Withdraw,
            Convert,
            down
        }
    }
}
</script>

<style scoped>
    .theDashBoardWrapper{
        padding: 36px 64px;
        width: 100%;
        height: 44.25%;
        display: flex;
        flex-direction: column;
    }
    .theDashBoardWrapper header{
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-bottom: auto;
    }
    .theDashBoardWrapper header > .title{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 40px;
        line-height: 48px;
        color: #FFFFFF;
    }
    .theDashBoardWrapper header > .manage{
        width: 117px;
        height: 43px;
        background: #2D2D2D;
        border-radius: 8PX;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #FFFFFF;
        opacity: 0.8;
    }
    .theDashBoardWrapper header > .manage:hover{
        opacity: 1;
    }
    .theDashBoardWrapper header > .manage:active{
        opacity: 0.8;
    }

    
    .theDashBoardWrapper main{
        margin-bottom: auto;
    }
    .theDashBoardWrapper main > .title{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 24px;
        line-height: 29px;
        color: #FFFFFF;
    }
    .theDashBoardWrapper main .balanceNumber{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 80px;
        line-height: 96px;
        color: #FFFFFF;
    }
    .theDashBoardWrapper main .balance{
        display: flex;
        align-items: center;
    }
    .theDashBoardWrapper main .trend{
        margin-top: -30px;
        margin-left: 19px;
        width: 73px;
        height: 30px;
        border: 1px solid #2EB17B;
        border-radius: 32px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .theDashBoardWrapper main .trendText{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 14px;
        line-height: 17px;
        color: #2EBE7B;
    }

    .theDashBoardWrapper footer{
        display: flex;
        justify-content: space-between;
    }
    .theDashBoardWrapper footer .date{
        display: flex;
    }
    .theDashBoardWrapper footer .date .line{
        height: 58px;
        border: 1px solid #333;
        margin-right: 32px;
    }
    .theDashBoardWrapper footer .item{
        margin-right: 40.75px;
    }
    .theDashBoardWrapper footer .date .item div > span{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #FFFFFF;
    }
    .theDashBoardWrapper footer .date .item div{
        margin-top: 8px;
    }
    .theDashBoardWrapper footer .date .item div > img{
        width: 10.38px;
        height: 10.38px;
        margin-left: 8.88px;
    }
    .theDashBoardWrapper footer .date .item .text{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 17px;
        line-height: 20px;
        color: #747474;
    }
    .theDashBoardWrapper footer .buttons{
        display: flex;
    }
    .theDashBoardWrapper footer .buttons button{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin-left: 30.5px;
        opacity: 0.6;
    }
    .theDashBoardWrapper footer .buttons button:hover{
        opacity: 1;
    }
    .theDashBoardWrapper footer .buttons button:active{
        opacity: 0.6;
    }
    .theDashBoardWrapper footer .buttons button img{
        margin-bottom: 10px;
    }
    .theDashBoardWrapper footer .buttons button > span{
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 17px;
        color: #d1d1d1;
    }

    @media (max-width: 1440px){
        .theDashBoardWrapper footer .date .line{
            margin-right: 16px;
        }
        .theDashBoardWrapper footer .item{
            margin-right: 20.375px;
        }
    }
    @media (max-width: 1280px){
        .theDashBoardWrapper footer .buttons button{
            margin-left: 15.25px;
        }
    }
    
</style>