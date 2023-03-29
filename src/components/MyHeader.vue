<script>
    export default {
        name:'MyHeader'
    }
</script>

<template>
    <div>
        <img id="logo" src="/logo.jpg" alt="">
        <h1>Yu-Gi-Oh Api</h1>
    </div>
</template>

<style lang="scss" scoped>
div{
    height: 80px;
    widows: 100%;
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
    
    #logo{
        height: 50px;
        padding: 0 10px;
    }
}

</style>