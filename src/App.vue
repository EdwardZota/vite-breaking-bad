<script>
  import axios from 'axios';

  import {store} from './AllCard.js'

  import MyHeader from './components/MyHeader.vue';
  import Selection from './components/Selection.vue';
  import Counter from './components/Counter.vue';
  import ListCard from './components/ListCard.vue';
  import LoadingPage from './components/LoadingPage.vue';


  export default {
    components:{
      MyHeader,
      Selection,
      Counter,
      ListCard,
      LoadingPage
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
          this.store.loading=false;
        })
      }
    },
    created(){
      this.GetCard();
    }
  }


</script>

<template>

  <LoadingPage/>

  <MyHeader/>

  <main>

    <ListCard/>

  </main>


  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
