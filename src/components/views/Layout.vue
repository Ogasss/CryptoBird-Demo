<template>
    <div class="layoutWrapper">
        <div class="asideWrapper">
            <Aside />
        </div>

        <div class="mainWrapper">

        </div>

        <div class="actionWrapper">

        </div>
    </div>
</template>

<script>
import Aside from '../Aside/Aside.vue'
export default {
    components:{
        Aside
    }
}
</script>

<style scoped>
    .layoutWrapper{
        width: 100%;
        height: 100%;
        display: flex;
    }
    .asideWrapper{        
        width: 13.75%;
        height: 100%;
    }
    .mainWrapper{
        border: 1px solid red;

        width: 54.59%;
        height: 100%;
    }
    .actionWrapper{
        border: 1px solid red;

        width: 31.66%;
        height: 100%;
    }
    
</style>