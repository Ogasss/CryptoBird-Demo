<template>
    <div class="theMyAssetsWrapper">
        <Header/>
        <Main/>
    </div>
</template>

<script>
import Header from './MyAssetsHeader.vue'
import Main from './MyAssetsMain.vue'
export default {
    components:{
        Header,
        Main
    }
}
</script>

<style>
    .theMyAssetsWrapper{
        height: 100%;
        width: 100%;
    }
</style>