<script>

import {store} from '../AllCard.js';
    
    export default {
        name:'Counter',
        data(){
            return{
                store
            }
        },
        computed:{
            numberOfResult(){
                return `Dalla tua ricerca hai ottenuto ${store.AllCard.length} risultati!`
            }
        }
    }

</script>

<template>
  
    <div class="counter">
        <span>{{numberOfResult}}</span>
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