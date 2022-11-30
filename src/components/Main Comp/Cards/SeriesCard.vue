<template>
	<div id="seriesCard">
		<div
			class="card"
			v-for="(elem, index) in propsToSeriesCard"
			:key="index"
		>
			<!-- Poster -->
			<div class="poster">
				<img
					:src="urlImgParziale + elem.poster_path"
					alt="Poster Non Disponibile"
				/>
			</div>

			<!-- Info FIlm  -->
			<div class="info">
				<!-- Titolo -->
				<div class="title">
					<span> Titolo: </span>
					<span> {{ elem.title }}</span>
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
				<div>
					<!-- Voto -->

					<!-- 1 Stella -->
					<div
						v-if="elem.vote_average >= 0 && elem.vote_average <= 2"
					>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
					</div>

					<!-- 2 Stella -->
					<div
						v-else-if="
							elem.vote_average >= 2 && elem.vote_average <= 4
						"
					>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
					</div>

					<!-- 3 Stella -->
					<div
						v-else-if="
							elem.vote_average >= 4 && elem.vote_average <= 6
						"
					>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
					</div>

					<!-- 4 Stella -->
					<div
						v-else-if="
							elem.vote_average >= 6 && elem.vote_average <= 8
						"
					>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
					</div>

					<!-- 5 Stella -->
					<div v-else>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
						<span
							><font-awesome-icon icon="fa-solid fa-star"
						/></span>
					</div>
				</div>

				<!--Lingua -->
				<!-- Inglese -->
				<div class="language" v-if="elem.original_language == 'en'">
					<img src="https://flagsapi.com/US/flat/64.png" />
				</div>
				<!-- Italiano -->
				<div
					class="language"
					v-else-if="elem.original_language == 'it'"
				>
					<img src="https://flagsapi.com/IT/flat/64.png" />
				</div>

				<!-- Mondiale -->
				<div class="language" v-else>
					<img src="../../../assets/mondo.png" alt="Lingua" />
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
		propsLinguaCard: String,
		propsGenereCard: String,
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