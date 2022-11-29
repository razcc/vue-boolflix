<template>
    <main>
        <FilmComp  :propsToFilmComp="propsFilm" />
    </main>
</template>

<script>
import FilmComp from './Main Comp/FilmComp.vue';
    export default {
        name: 'MainComp',
        props: {
            propsFilm: Array
        },
        components: {
            FilmComp,
        }
        
    }
</script>

<style lang="scss" scoped>
main{
    height: 90%;
    background-color: rgba(20, 20, 20, 1);
    color: white;
}
</style>