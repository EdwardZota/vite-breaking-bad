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
    width: 220px;
    background-color: variable.$primary-color;
    height: 450px;
    margin-bottom: 30px;
    text-align: center;
    position: relative;
    h3{
        color:variable.$secondary-color;
    }
    img{
        width: 100%;
        transition: all 1s;
        
        &:hover{
            filter: brightness(1.2);
            box-shadow: 0 0 20px 20px rgb(255, 0, 0);
            border-radius: 10px;
            animation: shake 0.82s cubic-bezier(.36,.07,.19,.97) both;
        }
        
    }
}

@keyframes shake {
  10%, 90% {
    transform: rotate(5deg);
  }
  
  20%, 80% {
    transform: rotate(-5deg);
  }

  30%, 50%, 70% {
    transform: rotate(10deg);
  }

  40%, 60% {
    transform: rotate(-10deg);
  }
}
</style>