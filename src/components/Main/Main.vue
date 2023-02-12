<template>
    <div class="theMainWrapper">
        <DashBoard/>
        <div class="theMainLine">

        </div>
        <Overview/>
    </div>
</template>

<script>
import DashBoard from './DashBoard.vue'
import Overview from './Overview.vue'
export default {
    components:{
        DashBoard,
        Overview
    }
}
</script>

<style scoped>
    .theMainWrapper{
        width: 100%;
        height: 100%;
        background: #101010;
    }
    .theMainLine{
        border: 1px solid #292929;
        height: 1px;
        width: 100%;
    }
</style>