<template>
    <div id="filmComp">
        <FilmCard :propsToFilmCard= "propsToFilmComp" />
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
    display: flex;
    flex-wrap: wrap;
}
</style>