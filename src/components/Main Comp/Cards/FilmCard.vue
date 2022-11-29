<template>
	<div id="filmCard">
		<div class="card" v-for="(elem, index) in propsToFilmCard" :key="index">
			<!-- Poster -->
			<div class="poster" >
				<img :src="urlImgParziale + elem.poster_path" alt="POSTER FILM" />
			</div>

			<!-- Info FIlm  -->
			<div class="info">
				<!-- Titolo -->
				<div class="title">
					{{ elem.title }}
				</div>

				<!-- Titolo Originale -->
				<div
					class="titoloOriginale"
					v-if="elem.title != elem.original_title"
				>
					<div>Titolo Originale:</div>
					<span>{{ elem.original_title }}</span>
				</div>

				<!-- Voto -->
				<div class="voto">
					<Span>Voto:</Span>
					<span>{{ elem.vote_average }}</span>
				</div>

				<!--Lingua -->

				<!-- Inglese -->
				<div class="language" v-if="elem.original_language == 'en'">
					<img src="../../../assets/ENGbandiera.png" alt="Lingia" />
				</div>

				<!-- Italiano -->
				<div
					class="language"
					v-else-if="elem.original_language == 'it'"
				>
					<img src="../../../assets/bandItalia.png" alt="Lingia" />
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
			arrayBandiere: [
				"../../../assets/bandItalia.png",
				"../../../assets/ENGbandiera.png",
			],
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