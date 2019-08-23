<template>
    <div class="header">
        <ul>
            <li v-for="(head,i) in header" :key="i">{{head.name}}</li>
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
    }
}
</script>
<style scoped lang="scss">
    .header {
        background: #161616;
        ul {
            li {
                display: inline-block;
                line-height: 1.2rem;
                margin-left: 0.4rem; 
                color: #afb1b3;
            }
        }
    }
</style>