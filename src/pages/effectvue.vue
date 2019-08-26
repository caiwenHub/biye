<template>
    <div class="effet-container" ref="effectPage">
        <h2>效果</h2>
        <div class="effet-content">
            <div class="notes">
                <ul>
                    <li v-for="(content,i) in contents" :key="i">
                        <span class="el-icon-star-on point"></span>
                        <span>{{content}}</span>
                    </li>
                </ul>
            </div>
            <div class="ec-content">
                <el-carousel trigger="click" height="">
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
                   {imgurl: require("../../static/content/4.png")},],
            contents: ["1.代码里有最全的注释，不怕你看不懂；",
                      "2.代码里清晰的逻辑，可以让你交流学习；",
                      "3.项目的文件目录命名规范，很轻松的找到对应文件；",
                      "4.代码引用文件标注清晰，告别没头脑",
                      "5.更简单，更快捷....."],
            effectHeight: ''
        }
    },
    mounted(){
        this.effectHeight = this.$refs.effectPage.offsetHeight
        localStorage.setItem('effectHeight',this.effectHeight)
    }
}
</script>
<style lang="scss" scoped>
    .effet-container {
        height: calc(100vh - 1.2rem);
        background: #fff;
        border: .4rem solid #F56C6C;
        h2 {
            font-weight: 800;
            line-height: 2rem;
        }
        .effet-content{
            display: block;
            .ec-content{
                margin: 0 20px;
                .show-img{
                    width: 100%;
                    height: 100%;
                }
            }
        }

        //当sreen大于769px生效
        @media screen and (min-width: 769px){
            .effet-content{
                display: flex;
                .notes{
                    width: 8rem;
                    background: #fff;
                    margin-left:  20px;
                    ul {
                        li{
                            line-height: .6rem;
                            text-align: left;
                            .point {
                                color: #E6A23C;
                            }
                        }
                    }
                }
                .ec-content{
                    flex: 1;
                    margin: 0 20px;
                }
            }
        }
    }

    //轮播样式
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

    
</style>