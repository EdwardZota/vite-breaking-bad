<script>

    export default {
        name:'OneCard',
        props:{
            image:String,
            name:String,
            spacies:String
        }
    }

</script>

<template>
  <div class="singleCard">
    <img :src="image" :alt="name">
    <h3>{{ name }}</h3>
    <h4>{{ spacies }}</h4>
  </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variable';

.singleCard{
    width: 250px;
    background-color: variable.$primary-color;
    height: 450px;
    margin-bottom: 30px;
    text-align: center;
    h3{
        color:variable.$secondary-color;
    }
    img{
        width: 100%;
    }
}

</style>