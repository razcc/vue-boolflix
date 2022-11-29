<template>
	<div id="filmCard">
		<div class="card" v-for="(elem, index) in propsToFilmCard" :key="index">
            <!-- Poster -->
            <div>

            </div>

            <!-- Titolo -->
            <div class="title">
                {{elem.title}}
            </div>
            
            <!-- Titolo Originale -->
            <div class="titoloOriginale">
                {{elem.original_title}}
            </div>

            <!--Lingua -->
            <div class="language">
                {{elem.original_language}}
            </div>

            <!-- Voto -->
            <div class="voto">
                {{elem.vote_average}}
            </div>
            
        </div>
	</div>
</template>

<script>
export default {
	name: "FilmCard",
	props: {
		propsToFilmCard: Array,
	},
};
</script>

<style lang="scss" scoped>
#filmCard{
    color: black;
    display: flex;
    flex-wrap: wrap;
}
.card{
    width: calc(100% / 8);
}
.card div{
    margin:10px;
    text-align: center;
}
</style>