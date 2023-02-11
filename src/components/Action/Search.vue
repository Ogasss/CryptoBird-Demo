<template>
    <div class="theSearchWrapper">
        <img class="searchIcon" :src="search" alt="">
        <input class="searchInput" type="text" placeholder="Search">
    </div>
</template>

<script>
import search from '../../assets/icons/Action/search.svg'
export default {
    setup(){
        return{
            search
        }
    }
}
</script>

<style scoped>
    .theSearchWrapper{
        width: 51.1%;
        height: 52px;
        margin-right: 16px;
        background: #101010;
        border-radius: 5px;
        display: flex;
        align-items: center;
    }
    .searchIcon{
        margin-left: 19.75px;
        opacity: 0.4;
    }
    .searchInput{
        margin-left: 11.75px;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 400;
        font-size: 16px;
        line-height: 19px;
        display: flex;
        align-items: center;
        color: #747474;
    }
    .searchInput:focus{
        color: #FFF;
    }
    .searchIcon:hover{
        opacity: 1;
    }
</style>