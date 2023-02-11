<template>
    <a class="theOptionWrapper">
        <img class="theOptionIcon" :src="src">
        <span class="theOptionText">{{text}}</span>
    </a>
</template>

<script>
export default {
    props:{
        src: String,
        text: String
    },
    setup(props){
        const {src,text} = props
        return {
            src,text
        }
    }
}
</script>

<style scoped>
    .theOptionWrapper{
        display: flex;
        align-items: center;
        transition: all 0.3s ease;
        opacity: 0.4;
        margin-bottom: 32px;
    }
    .icon{
        width: 22px;
        height: 22px;
    }
    .theOptionText{
        margin-left: 24px;
        color: #FFFFFF;
        font-family: 'Aeonik';
        font-style: normal;
        font-weight: 500;
        font-size: 17px;
        line-height: 20px;
        display: flex;
        align-items: center;
    }
    .theOptionWrapper:hover{
        opacity: 1;
    }
    @media (max-width: 1500px){
        .theOptionText{
            display: none;
        }
        .theOptionWrapper{
            justify-content: center;
        }
    }
</style>