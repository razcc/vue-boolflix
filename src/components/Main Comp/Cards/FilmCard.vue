<template>
	<div id="filmCard">
		<div class="card" v-for="(elem, index) in propsToFilmCard" :key="index">
			<!-- Poster -->
            <div class="poster">
                <img :src="urlImgParziale + elem.poster_path" alt="Immagine">
            </div>
			<!-- Info FIlm  -->
			<div class="info">
				<!-- Titolo -->
				<div class="title">
					{{ elem.title }}
				</div>

				<!-- Titolo Originale -->
				<div class="titoloOriginale">
					{{ elem.original_title }}
				</div>

				<!--Lingua -->
				<div class="language">
					{{ elem.original_language }}
				</div>

				<!-- Voto -->
				<div class="voto">
					{{ elem.vote_average }}
				</div>
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
    data(){
        return{
            urlImgParziale: "https://image.tmdb.org/t/p/w185/",
        }
    }
};
</script>

<style lang="scss" scoped>
#filmCard {
	color: black;
	display: flex;
	flex-wrap: wrap;
	gap: 20px;
}
.card {
	width: calc(100% / 8 - 20px);
	margin-bottom: 20px;
    position: relative;
    overflow: hidden;
}
.poster{
    transition: all 2s;
}
.poster img{
width: 100%;

}

.info {
    background-color: black;
    color: white;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: translateX(100%);
    transition: all 2s;

}

.card:hover .poster{
    transform: translateX(-100%) rotateY(-360deg);
}
.card:hover .info{
    transform: translateX(0%) rotateY(360deg);
}

</style>