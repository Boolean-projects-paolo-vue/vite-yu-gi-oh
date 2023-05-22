<script>
    export default{
       props:{
        characterCard: Object,
       } 
    }
</script>

<template>
  
  <div class="card">
    <img :src="characterCard.card_images[0].image_url_small" :alt="characterCard.id">
    <p class="p-2" style="text-transform: uppercase; color: white; font-weight: 700;"> {{ characterCard.name }}</p>
    <div>{{ characterCard.archetype }}</div>
  </div>
 
  
</template>

<style lang="scss" scoped>

  
  .card{
    margin-inline: 0.5rem;
    margin-bottom: 1rem;
    width: 18%;
    background-color:#D48F38;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 12px;
  }
</style>