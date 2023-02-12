<template>
    <div class="layoutWrapper">
        <div class="asideWrapper">
            <Aside/>
        </div>

        <div class="mainWrapper">
            <Main/>
        </div>

        <div class="actionWrapper">
            <Action/>
        </div>
    </div>
</template>

<script>
import Aside from '../Aside/Aside.vue'
import Action from '../Action/Action.vue'
import Main from '../Main/Main.vue'
export default {
    components:{
        Aside,
        Action,
        Main
    }
}
</script>

<style scoped>
    .layoutWrapper{
        width: 100vw;
        min-width: 1215px;
        /* height: 1200px; */
        height: 100vh;
        min-height: 920px;
        display: flex;
        overflow: hidden;
    }
    .asideWrapper{        
        width: 13.75%;
        height: 100%;
        /* display: none; */
    }
    .mainWrapper{
        width: 54.59%;
        height: 100%;
    }
    .actionWrapper{
        width: 31.66%;
        height: 100%;
        /* display: none; */
    }
    
</style>