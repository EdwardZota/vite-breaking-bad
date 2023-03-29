<script>

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
    }
  }


</script>

<template>

  <MyHeader/>

  <main>
    <Selection/>

    <ListCard/>

  </main>

  
</template>

<style lang="scss">
@use "./styles/general.scss";

</style>
