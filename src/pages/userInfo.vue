<template>
    <div class="user-info">
        <div class="user-form">
            <el-form label-position="top" label-width="0" :model="userInf">
                <el-form-item label="名称">
                    <el-input v-model="userInf.name"></el-input>
                </el-form-item>
                <el-form-item label="活动区域">
                    <el-input v-model="userInf.region"></el-input>
                </el-form-item>
                <el-form-item label="活动形式">
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
            }
        }
    },
    methods: {
        submitForm() {
        },
        resetForm() {
            this.userInf = {name: '',region: '',type: ''}
        }
    }
}
</script>
<style lang="scss" scoped>
    .user-info{
        height: 12rem;
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
            height: 12rem;
            display: flex;
            justify-content: center;
            align-items: center;
            .user-form{
                width: 4rem;
            }
        }
    }
</style>