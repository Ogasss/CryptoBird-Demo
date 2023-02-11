<template>
    <div class="theHeaderWrapper">
        <Search class="theSearch"/>

        <img class="email" :src="email" alt="">

        <img class="message" :src="message" alt="">

        <img class="profile" :src="profile" alt="">
    </div>
</template>

<script>
import email from '../../assets/icons/Action/email.svg'
import message from '../../assets/icons/Action/message.svg'
import profile from '../../assets/icons/Action/profile.jpg'

import Search from './Search.vue'

export default {
    components:{
        Search
    },
    setup(){
        return{
            email,
            message,
            profile
        }
    }
}
</script>

<style scoped>
    .theHeaderWrapper{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .theHeaderWrapper > .email{
        opacity: 0.4;
        margin-right: 26px;
    }
    .theHeaderWrapper > .email:hover{
        opacity: 1;
    }
    .theHeaderWrapper > .message{
        opacity: 0.4;
        margin-right: 40px;
    }
    .theHeaderWrapper > .message:hover{
        opacity: 1;
    }
    .theHeaderWrapper > .profile{
        width: 40px;
        height: 40px;
        border-radius: 50%;
        opacity: 0.8;
    }
    .theHeaderWrapper > .profile:hover{
        opacity: 1;
    }
    @media (max-width: 1300px){
        .email{
            display: none;
        }
        .message{
            display: none
            ;
        }
        .theSearch{
            width: 80%;
        }
    }
</style>