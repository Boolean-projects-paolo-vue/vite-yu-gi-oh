<script>
    import CharacterCard from './CharacterCard.vue';
    import { store } from '../../store';
    export default {
        data() {
            return {
                store,
            }
        },
        components: {
            CharacterCard,
        }
    }
</script>

<template>
    <div class="found"><div class="sub_found">hei</div></div>
    <div class="card_container">
        <CharacterCard v-for="character in store.CharacterList" 
        :key="character.id"
        class="card" 
        :characterCard="character" 
        />
    </div>
</template>

<style lang="scss" scoped>
    .card_container{
        max-width: 50%;
        margin: auto;
        background-color: white;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        padding-inline: 1rem;
        text-align: center;
    }

    .found{
        width: 50%;
        margin: auto;
        background-color: white;
        height:5rem;
        display: flex;
        justify-content: center;
        align-items: center;
        padding-top: 2rem;
    }
    
    .sub_found{
        width: 94%;
        background-color: black;
        height: 100%;
    }

    
</style>