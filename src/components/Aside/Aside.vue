<template>
    <div class="theAsideWrapper">
        <header class="title">
            <img :src="logo"/>
            <span class="titleText">
                CryptoBird
            </span>
        </header>

        <main class="main">
            <div v-for="option in optionArr" :key="option[1]">
                <Option :src="option[0]" :text="option[1]"/>
            </div>

            <div class="logOut">
                <Option :src="AsideOption7" :text="option7Text"/>
            </div>
        </main>
        
        
    </div>
</template>

<script>
import logo from '../../assets/icons/Aside/logo.svg'
import AsideOption1 from '../../assets/icons/Aside/AsideOption1.svg'
import AsideOption2 from '../../assets/icons/Aside/AsideOption2.svg'
import AsideOption3 from '../../assets/icons/Aside/AsideOption3.svg'
import AsideOption4 from '../../assets/icons/Aside/AsideOption4.svg'
import AsideOption5 from '../../assets/icons/Aside/AsideOption5.svg'
import AsideOption6 from '../../assets/icons/Aside/AsideOption6.svg'
import AsideOption7 from '../../assets/icons/Aside/AsideOption7.svg'
import Option from './Option.vue'

export default {
    components:{
        Option,
    },
    setup(){
        const optionArr = [
            [AsideOption1,'Dashboard'],
            [AsideOption2,'Wallet'],
            [AsideOption3,'Trade'],
            [AsideOption4,'Market'],
            [AsideOption5,'Notification'],
            [AsideOption6,'Settings'],
        ]

        const option7Text = `Log out`
        return{
            logo,
            optionArr,
            AsideOption7,
            option7Text
        }
    }
}
</script>

<style scoped>
    .theAsideWrapper{
        padding: 40px 32px;
        min-width: 88px;
        height: 100vh;
        background: #1A1A1A;
    }
    .title{
        display: flex;
        align-items: center;
        margin-bottom: 80px;
    }
    .titleLogo{
        width: 40px;
        height: 40px;
    }
    .titleText{
        margin-left: 17px;
        color: #FFFFFF;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 22px;
        line-height: 26px;
    }
    .logOut{
        margin-top: calc(100vh - 460px - 40px);
    }
    @media (max-width: 1500px){
        .titleText{
            display: none;
        }
        .title{
            justify-content: center;
        }
        .logOut{
        }
    }
    @media (max-height:530px){
        .main{
            display: none;
        }
        .theWrapper{
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }
</style>