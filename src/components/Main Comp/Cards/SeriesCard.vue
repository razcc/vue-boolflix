<template>
	<div id="seriesCard">
		<div class="card" v-for="(elem, index) in propsToSeriesCard"  :key="index" >

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
	name: "SeriesCard",
	props: {
		propsToSeriesCard: Array,
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


#seriesCard {
	display: flex;
	flex-wrap: wrap;
	gap: 20px;
	@include cardStyle;

}

</style>