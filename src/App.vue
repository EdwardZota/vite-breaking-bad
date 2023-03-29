<script>
  import axios from 'axios';

  import {store} from './AllCard.js'

  import MyHeader from './components/MyHeader.vue';
  import Selection from './components/Selection.vue';
  import Counter from './components/Counter.vue';
  import ListCard from './components/ListCard.vue';


  export default {
    components:{
      MyHeader,
      Selection,
      Counter,
      ListCard
    },
    data(){
      return{
        store
      }
    },
    methods:{
      GetCard(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then(response =>{
          this.store.AllCard = response.data.data;
        })
      }
    },
    created(){
      this.GetCard();
    }
  }


</script>

<template>

  <MyHeader/>

  <main>

    <ListCard/>

  </main>

  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
