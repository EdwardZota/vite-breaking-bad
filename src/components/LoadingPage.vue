<script>

import{store} from '../AllCard.js';

export default{
    name:'LoadingPage',
    data(){
        return{
            store
        }
    }
}

</script>

<template>
    <div class="loading" v-if="store.loading">
        <h1>Attendi il caricamento...</h1>
    </div>
</template>

<style lang="scss" scoped>
.loading {
        position: fixed;
        z-index: 999;
        top: 0;
        left: 0;
        background-color: white;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 40px;
    }
</style>