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
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(response =>{
          this.store.AllCard = response.data.data;
          this.store.loading=false;
        })
      },
      GetCardArchetype(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(response =>{
          this.store.AllCardArchetype = response.data;
        })
      },
      SelectArchetype(){
        let urlApi = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
        
        urlApi +=`?archetype=${this.store.selected}`;

        axios.get(urlApi)
        .then(response =>{
          this.store.AllCard = response.data.data;
        })
      }
    },
    created(){
      this.GetCard();
      this.GetCardArchetype();
    }
  }


</script>

<template>

  <LoadingPage/>


  <MyHeader/>
  
  <Selection  @change="SelectArchetype()"/>
  <main>
    <Counter/>
    <ListCard/>

  </main>


  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
