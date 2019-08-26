<template>
    <div class="header">
        <div class="header-img">
            <span class="iconfont icon-biye"></span>
            <span class="header-word">Biyebang</span>
        </div>
        <ul>
            <li v-for="(head,i) in header" :key="i" @click="goTo">{{head.name}}</li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
        return {
            header: [{name: "首页"},
                    {name: "步骤"},
                    {name: "详情"},
                    {name: "联系我们"}]
        }
    },
    methods: {
      goTo(){
          this.$emit('goTo')
      }  
    },
}
</script>
<style scoped lang="scss">
    @font-face {
        font-family: yishu;
        src: url('../../static/font_family/Cute_Font.ttf');
    }
    .header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background: #409EFF;
        z-index: 100;
        padding: 0 .4rem;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        .header-img{
            .icon-biye{
                font-size: .8rem;
            }
            .header-word{
                font-style: oblique;
                font-family: yishu;
                font-size: .8rem;
                color: #fff;
                font-weight: 600;
            }
        }
        ul {
            li {
                display: inline-block;
                line-height: 1.2rem;
                margin-left: 0.4rem; 
                color: #fff;
                &:hover{
                    cursor: pointer;
                }
            }
        }
    }
</style>