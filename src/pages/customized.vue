<template>
    <div class="customized">
        <h2>定制</h2>
        <div class="c_content">
            <ul>
                <li v-for="(content,i) in contents" :key="i">{{content.item}}</li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            contents: [{item: "指定使用的语言&软件&技术"},
                        {item: "指定环境与平台要求"},
                        {item: "指定设计风格与排班模式"},
                        {item: "定制全套模式 or not"},
                        {item: "定制演讲稿&PPT"}]
        }
    }
}
</script>
<style lang="scss" scoped>
    .customized {
        height: 12rem;
        h2 {
            font-weight: 600;
            padding-left: 20px;
            line-height: 100px;
            text-align: left;
        }
        .c_content{
            height: 10rem;
            display: flex;
            justify-content: center;
            align-items: center;
            ul {
                li {
                    line-height: 1rem;
                }
            }
        }
    }
</style>