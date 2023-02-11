<template>
    <div class="layoutWrapper">
        <div class="asideWrapper">
            <Aside/>
        </div>

        <div class="mainWrapper">

        </div>

        <div class="actionWrapper">
            <Action/>
        </div>
    </div>
</template>

<script>
import Aside from '../Aside/Aside.vue'
import Action from '../Action/Action.vue'
export default {
    components:{
        Aside,
        Action
    }
}
</script>

<style scoped>
    .layoutWrapper{
        width: 1920px;
        height: 1200px;
        display: flex;
    }
    .asideWrapper{        
        width: 13.75%;
        height: 100%;
        /* display: none; */
    }
    .mainWrapper{
        width: 54.59%;
        height: 100%;
        /* display: none; */
    }
    .actionWrapper{
        width: 31.66%;
        height: 100%;
    }
    
</style>