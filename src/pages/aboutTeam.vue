<template>
    <div class="footer-team" ref="teamPage">
        
    </div>
</template>
<script>
export default {
    mounted(){
        this.teamHeight = this.$refs.teamPage.offsetHeight
        localStorage.setItem('teamHeight',this.teamHeight)
    }
}
</script>
<style lang="scss" scoped>
    .footer-team{
        height: 1rem;
        background: rgb(41, 25, 85);
    }
    @media screen and (min-width: 769px){
        .footer-team{
            height: 6rem;
            background: rgb(41, 25, 85);
        }
    }
</style>