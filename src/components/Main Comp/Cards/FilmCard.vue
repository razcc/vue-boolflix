<template>
	<div id="filmCard">
		<div class="card" v-for="(elem, index) in propsToFilmCard" :key="index">
			<!-- Poster -->
			<div class="poster">
				<img :src="urlImgParziale + elem.poster_path" alt="Immagine" />
			</div>

			<!-- Info FIlm  -->
			<div class="info">
				<!-- Titolo -->
				<div class="title">
					{{ elem.title }}
				</div>

				<!-- Titolo Originale -->
				<div class="titoloOriginale">
					<div>Titolo Originale:</div>
					<span>{{ elem.original_title }}</span>
				</div>

				<!--Lingua -->
				<div class="language">
					{{ elem.original_language }}
				</div>

				<!-- Voto -->
				<div class="voto">
					<Span>Voto:</Span>
					<span>{{ elem.vote_average }}</span>
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
	data() {
		return {
			urlImgParziale: "https://image.tmdb.org/t/p/w185/",
		};
	},
};
</script>

<style lang="scss" scoped>
@import "../../MIXIN/mixinCard.scss";
#filmCard {
	display: flex;
	flex-wrap: wrap;
	gap: 40px;
	@include cardStyle;
}
</style>