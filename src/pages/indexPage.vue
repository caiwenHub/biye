<template>
    <div class="index-container" ref="indexPage">
        <div class="index-left"></div>
        <div class="index-right"></div>
        <div class="index-conten">
            <h1>毕业帮</h1>
            <div class="ic_content">
                学习使我快乐!!!!
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            indexHeight: ''
        }
    },
    mounted(){
        this.indexHeight = this.$refs.indexPage.offsetHeight
        localStorage.setItem('indexHeight',this.indexHeight)
    }
}
</script>
<style lang="scss" scoped>
    .index-container {
        position: relative;
        margin-top: 1.2rem;
        height: calc(100vh - 1.2rem);
        background: #fff;
        // background: rgba(64, 158, 255,0.4);
        display: flex;
        justify-content: center;
        align-items: center;
        .index-left{
            position: absolute;
            height: calc(100vh - 1.2rem);
            width: calc(50vw - .155rem);
            left: 0;
            top: 0;
            background: rgb(228, 149, 149);
            opacity: 0.4;
            animation: move 5s ease-out 4s;
            animation-fill-mode:forwards;
        }
        .index-right{
            position: absolute;
            height: calc(100vh - 1.2rem);
            width: calc(50vw - .15rem);
            top: 0;
            right: 0;
            background: rgb(228, 149, 149);
            opacity: 0.4;
            animation: move 5s ease-out 4s;
            animation-fill-mode:forwards;
        }
        @keyframes move {
            from {width: calc(50vw - .15rem);}
            to {width: .4rem}
        }
    }
</style>