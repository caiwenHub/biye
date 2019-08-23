<template>
    <div class="effet-container">
        <h2>效果</h2>
        <div class="effet-content">
            <div class="notes">毕业帮</div>
            <div class="ec-content">
                <el-carousel trigger="click" height="8rem">
                <el-carousel-item v-for="item in 4" :key="item">
                    <h3>{{ item }}</h3>
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
        }
    }
}
</script>
<style lang="scss" scoped>
    .effet-container {
        height: 12rem;
        background: #409EFF;
        
    }
    h2 {
            font-weight: 800;
            line-height: 2rem;
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
                width: 200px;
                background: #fff;
                margin: 0 20px;
            }
            .ec-content{
                flex: 1;
            }
        }
    }
</style>