<template>
    <div class="user-info" ref="userPage">
        <div class="user-form">
            <el-form label-position="right" label-width="150px" :model="userInf">
                <el-form-item label="姓名">
                    <el-input v-model="userInf.name"></el-input>
                </el-form-item>
                <el-form-item label="联系方式">
                    <el-input v-model="userInf.region"></el-input>
                </el-form-item>
                <el-form-item label="题目名称">
                    <el-input v-model="userInf.type"></el-input>
                </el-form-item>
                <el-form-item>
                    <el-button type="primary" @click="submitForm()">提交</el-button>
                    <el-button @click="resetForm()">重置</el-button>
                </el-form-item>
            </el-form>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            userInf: {
                name: '',
                region: '',
                type: ''
            },
            userHeight: ''
        }
    },
    methods: {
        submitForm() {
        },
        resetForm() {
            this.userInf = {name: '',region: '',type: ''}
        }
    },
    mounted(){
        this.userHeight = this.$refs.userPage.offsetHeight
        localStorage.setItem('userHeight',this.userHeight)
    }
}
</script>
<style lang="scss" scoped>
    .user-info{
        height: calc(100vh - 1.2rem);
        display: flex;
        justify-content: center;
        align-items: center;
        .user-form{
            width: 12rem;
        }
    }
    //当宽度小于769生效
    @media screen and (max-width: 769px){
        .user-info{
            margin-top: 1.2rem;
            height: calc(100vh - 1.2rem);
            display: flex;
            justify-content: center;
            align-items: center;
            .user-form{
                width: 4rem;
            }
        }
    }
</style>