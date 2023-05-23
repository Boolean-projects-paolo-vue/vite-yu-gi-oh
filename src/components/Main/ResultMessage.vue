<script>
  import { store } from '../../store';

  export default {
      data() {
          return {
              store,
          }
      },
  };
</script>

<template>
  <div style="color:white">Found {{ store.CharacterList.length }} Cards</div>
</template>

<style lang="scss" scoped>

</style>