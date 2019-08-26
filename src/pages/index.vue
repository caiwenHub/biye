<template>
    <div>
        <div class="header">
            <div class="header-img">
                <span class="iconfont icon-biye"></span>
                <span class="header-word">Biyebang</span>
            </div>
            <ul>
                <li v-for="(head,i) in header" :key="i" @click="goTo(head.name)">{{head.name}}</li>
            </ul>
        </div>
        <index-page></index-page>
        <customized-vue></customized-vue>
        <effect-vue></effect-vue>
        <user-info></user-info>
        <about-team></about-team>
    </div>
</template>
<script>
import customizedVue from './customized'
import indexPage from './indexPage'
import effectVue from './effectvue'
import userInfo from './userInfo'
import aboutTeam from './aboutTeam'
export default {
    components: {
        customizedVue,
        indexPage,
        effectVue,
        userInfo,
        aboutTeam
    },
    mounted(){
        window.addEventListener('scroll',function(){
            let scrollTop = window.pageYOffset;
            console.log(scrollTop)
        })
    },
    data(){
        return {
            header: [{name: "首页"},
                    {name: "步骤"},
                    {name: "展示"},
                    {name: "登记"},
                    {name: "联系我们"}]
        }
    },
    methods: {
        goTo(val){
            let teamHeight = localStorage.getItem('teamHeight')
            let customHeight = localStorage.getItem('customHeight')
            let effectHeight = localStorage.getItem('effectHeight')
            let indexHeight = localStorage.getItem('indexHeight')
            let userHeight = localStorage.getItem('userHeight')
            switch (val){
                case "首页":
                    console.log(indexHeight);
                    this.move(0);
                    break;
                case "步骤":
                    document.documentElement.scrollTop = customHeight;
                    console.log(customHeight);
                    break;
                case "展示":
                    document.documentElement.scrollTop = effectHeight*2;
                    console.log(effectHeight);
                    break;
                case "登记": 
                    document.documentElement.scrollTop = effectHeight*3;
                    console.log(userHeight);
                    break;
                case "联系我们":
                    document.documentElement.scrollTop = effectHeight*4;
                    console.log(teamHeight);
                    break;
                default :
                    break;
            }
        },
        move(top){
            // let timmer = null;
            // if(val <= 100||timmer){
            //     clearInterval(timmer)
            // }else{
                if(timmer){
                    clearInterval(timmer)
                }
                let timmer = setInterval(() => {
                    document.documentElement.scrollTop = document.documentElement.scrollTop-50;
                    if(document.documentElement.scrollTop===top){
                        clearInterval(timmer);
                    }
                }, 20);
            // }
        }  
    }
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