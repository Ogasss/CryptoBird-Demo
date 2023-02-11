<template>
    <div class="theMyAssetsWrapper">
        <div>
            <Header/>
        </div>
        <div>
            <Main/>
        </div>
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