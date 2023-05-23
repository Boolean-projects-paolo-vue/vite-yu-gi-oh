<script>
    import { store } from '../../store'
    export default{
        data(){
            return{
                store,
            };
            
        },
        methods: {
            emitArch() {
                this.$emit('performSearch')
            }
        },
    }
</script>

<template>
    <div class="search">
        
        <select id="menu" name="opzioni" v-model="store.SearchArr" @change="emitArch">
            <option value="">Select status</option>
            <option v-for="archetype in store.Archetypes" :key="archetype.archetype_name" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
        </select>
       
    </div>
</template>

<style lang="scss" scoped>
    .search{
        max-width: 50%;
        height: 100%;
        margin: auto;
        padding: 2vh;
        height: 6vh;
        display: flex;
        align-items: center;
    }
</style>