<template>
    <div class="customized" ref="customPage">
        <h2>定制</h2>
        <div class="c_content">
            <ul>
                <li v-for="(content,i) in contents" :key="i">{{content.item}}</li>
            </ul>
            <div class="tips">
                <ul>
                    <li v-for="(tip,i) in tips_icons" :key="i" class="tip">
                        <div class="tip-content">
                            <i :class="tip.icon"></i>
                            <span>{{tip.name}}</span>
                        </div>
                        <span class="el-icon-d-arrow-right" v-if="tip.name!=='解决疑点'"></span>
                        <!-- <span class="iconfont icon-buzhoutiao"></span> -->
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
import '../../static/font/iconfont.css'
export default {
    data(){
        return {
            contents:[{item: "指定使用的语言&软件&技术"},
                        {item: "指定环境与平台要求"},
                        {item: "指定设计风格与排班模式"},
                        {item: "定制全套模式 or not"},
                        {item: "定制演讲稿&PPT"}],
            tips_icons:[{name: '了解需求', icon: 'iconfont icon-lejie'},
                        {name: '制定方案', icon: 'iconfont icon-fangan'},
                        {name: '确定方案', icon: 'iconfont icon-fangancopy'},
                        {name: '交付定金', icon: 'iconfont icon-weikuan'},
                        {name: '实施方案', icon: 'iconfont icon-shishi'},
                        {name: '方案完成', icon: 'iconfont icon-jiejuefangan'},
                        {name: '尾款交付', icon: 'iconfont icon-weikuan'},
                        {name: '解决疑点', icon: 'iconfont icon-yanshi1'}]
        }
    },
    mounted(){
        this.customHeight = this.$refs.customPage.offsetHeight
        localStorage.setItem('customHeight',this.customHeight)
    }
}
</script>
<style lang="scss" scoped>
    .customized {
        height: calc(100vh - 1.2rem);
        h2 {
            font-weight: 600;
            padding-left: 20px;
            line-height: 100px;
            text-align: left;
        }
        .c_content{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            ul {
                li {
                    line-height: 1rem;
                }
            }
        }
        .tips{
            .tip{
                display: inline-block;
                .tip-content{
                    padding: 0 0.1rem;
                    display: inline-block;
                    width: 1.8rem;
                    line-height: 1.8rem;
                    border-radius: .9rem;
                    background-color: #F56C6C;
                    color: #fff;
                }
                span {
                    display: inline-block;
                }
            }   
        }
        
    }
</style>