<template>
	<div id="seriesCard">
		<div class="card" v-for="(elem, index) in propsToSeriesCard" :key="index">

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
#seriesCard {
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
.poster {
	transition: all 2s;
}
.poster img {
	width: 100%;
}

// Info FIlm
.info {
	background: rgb(63, 94, 251);
	background: radial-gradient(
		circle,
		rgba(63, 94, 251, 1) 0%,
		rgba(246, 11, 59, 1) 100%
	);
	color: white;
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	transform: translateX(100%);
	transition: all 2s;
	text-align: center;
	padding: 30px 20px;
	overflow: auto;
}
.title {
	font-size: 30px;
	font-weight: bold;
}
.titoloOriginale {
	font-size: 20px;
	font-weight: bold;
}
.info div {
	margin-bottom: 20px;
}

.card:hover .poster {
	transform: translateX(-100%) rotateY(-360deg);
}
.card:hover .info {
	transform: translateX(0%) rotateY(360deg);
}
</style>