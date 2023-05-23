<script>
  import FilterCard from "./components/Main/FilterCard.vue";
  import CharacterList from "./components/Main/CharacterList.vue";
  import axios from 'axios';
  import { store } from "./store"

  export default {
    data() {
      return {
        store,
      };
    },
    components: {
      FilterCard, 
      CharacterList,
    },

    methods: {
      requestDataFromApi(){
        axios
          .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
          .then(response => (this.store.Archetypes = response.data));
      },
      requestApiFilter(){
        axios
          .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?', {
            params: {
              archetype: this.store.SearchArr,
            }
          })
          .then(response => (this.store.CharacterList = response.data.data));
      }


    },
    created() {
    this.requestDataFromApi();

    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=105&offset=0')
      .then(response => ( this.store.CharacterList = response.data.data ));
    },
  };
  

</script>


<template>
  <h1 class="p-1"><img src="https://3.bp.blogspot.com/-wLH_qbmRoJU/TZdYCkrQuZI/AAAAAAAAAw0/G1_uzsANMI8/s1600/yugioh+logo.png" alt="" style="height: 20px;"> Yu-Gi-Oh Api</h1>

  <main class="main">
    <FilterCard @performSearch="requestApiFilter"/>
    <CharacterList />
  </main>

</template>


<style lang="scss">
  @import "../node_modules/bootstrap/scss/bootstrap";

  .main{
    background-color:#D48F38;
    height: 100%;
    padding-bottom:2rem;
  }

</style>
