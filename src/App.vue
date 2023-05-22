<script>
  import AppSearch from "./components/Main/AppSearch.vue";
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
      AppSearch, 
      CharacterList,
    },
    created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => ( this.store.CharacterList = response.data.data ));
    },
  };
  

</script>


<template>
  <h1 class="p-1"><img src="https://3.bp.blogspot.com/-wLH_qbmRoJU/TZdYCkrQuZI/AAAAAAAAAw0/G1_uzsANMI8/s1600/yugioh+logo.png" alt="" style="height: 20px;"> Yu-Gi-Oh Api</h1>

  <main class="main">
    <AppSearch />
    <ResultMessage />
    <CharacterList />
  </main>

</template>


<style lang="scss">
  @import "../node_modules/bootstrap/scss/bootstrap";

  .main{
    background-color:#D48F38;
    height: 100%;
  }

</style>
