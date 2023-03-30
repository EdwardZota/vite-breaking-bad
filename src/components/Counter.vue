<script>

import {store} from '../AllCard.js';
    
    export default {
        name:'Counter',
        data(){
            return{
                store
            }
        }
    }

</script>

<template>
  
    <div class="counter">
        <span>La tua ricerca ha trovato TOT risultati</span>
    </div>
</template>

<style lang="scss">

.counter{
    background-color: black;
    width: 100%;
    height: 50px;
    color: white;
    line-height: 50px;
    padding-left: 30px;
    span{
        font-weight: bolder;
    }
}

</style>