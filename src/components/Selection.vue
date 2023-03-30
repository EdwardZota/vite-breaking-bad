<script>

    import {store} from '../AllCard.js';
    
    export default {
        name:'Selection',
        data(){
            return{
                store
            }
        }
    }

</script>

<template>
    <div class="container">
    <select id="archetype" v-model="store.selected" @change="$emit('change')">
        <option v-for="(name,i) in store.AllCardArchetype" :key="i" :value="name.archetype_name">{{name.archetype_name}}</option>
    </select>

    </div>
</template>

<style lang="scss">

.container{
    width: 1300px;
    margin: 20px auto;
    
    #archetype{
        font-size: 20px;
    }
}
</style>