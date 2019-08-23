<template>
    <div class="effet-container">
        <h2>效果</h2>
        <div class="effet-content">
            <div class="notes">毕业帮</div>
            <div class="ec-content">
                <el-carousel trigger="click" height="8rem">
                <el-carousel-item v-for="(img,i) in imgs" :key="i">
                    <img class="show-img" :src="img.imgurl" :alt="i">
                </el-carousel-item>
                </el-carousel>
            </div>
        </div>
    </div>
</template>
<script>
import 'element-ui/lib/theme-chalk/index.css'
export default {
    data(){
        return {
            imgs: [{imgurl: require("../../static/content/1.png")},
                   {imgurl: require("../../static/content/2.png")},
                   {imgurl: require("../../static/content/3.png")},
                   {imgurl: require("../../static/content/4.png")},]
        }
    }
}
</script>
<style lang="scss" scoped>
    .effet-container {
        height: 100vh;
        background: #409EFF;
        
    }
    .ec-content{
        margin: 0 20px;
    }
    h2 {
        font-weight: 800;
        line-height: 2rem;
    }
    .show-img{
        width: 100%;
        height: 100%;
    }
    .effet-content{
        display: block;
    }
    .el-carousel__item h3 {
        color: #475669;
        font-size: 14px;
        opacity: 0.75;
        line-height: 150px;
        margin: 0;
    }

    .el-carousel__item:nth-child(2n) {
        background-color: #99a9bf;
    }
    
    .el-carousel__item:nth-child(2n+1) {
        background-color: #d3dce6;
    }
    @media screen and (min-width: 769px){
        .effet-content{
            display: flex;
            .notes{
                width: 8rem;
                background: #fff;
                margin-left:  20px;
            }
            .ec-content{
                flex: 1;
                margin: 0 20px;
            }
        }
    }
</style>