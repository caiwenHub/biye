<template>
    <div>
        <header-vue></header-vue>
        <index-page></index-page>
        <customized-vue></customized-vue>
        <effect-vue></effect-vue>
        <user-info></user-info>
        <about-team></about-team>
    </div>
</template>
<script>
import headerVue from './header'
import customizedVue from './customized'
import indexPage from './indexPage'
import effectVue from './effectvue'
import userInfo from './userInfo'
import aboutTeam from './aboutTeam'
export default {
    components: {
        headerVue,
        customizedVue,
        indexPage,
        effectVue,
        userInfo,
        aboutTeam
    }
}
</script>
<style scoped lang="scss">
    
</style>