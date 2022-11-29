<template>
    <div id="filmComp">
        <div>
            <FilmCard :propsToFilmCard= "propsToFilmComp" />
        </div>
        
    </div>
</template>

<script>
import FilmCard from './Cards/FilmCard.vue';

    export default {
        name: "FilmComp",
        props: {
            propsToFilmComp: Array
        },
        components: {
            FilmCard,
            
        },

        
    }
</script>

<style lang="scss" scoped>
#filmComp{
    padding: 30px;
    width: 90%;
    margin: auto;
    
}
</style>