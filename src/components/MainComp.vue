<template>
	<main>
		<div>
			<div class="filmsTitle">
				<h2>Films</h2>
			</div>
			<FilmComp :propsToFilmComp="propsFilm" />
		</div>

		<div>
			<div class="seriesTitle">
				<h2>Series</h2>
			</div>

			<SeriesComp :propsToSeriesComp="propsSeries" />
		</div>
	</main>
</template>

<script>
import FilmComp from "./Main Comp/FilmComp.vue";
import SeriesComp from "./Main Comp/SeriesComp.vue";

export default {
	name: "MainComp",
	props: {
		propsFilm: Array,
		propsSeries: Array,
	},
	components: {
		FilmComp,
		SeriesComp,
	},
};
</script>

<style lang="scss" scoped>
main {
	height: 90%;
	background-color: rgba(20, 20, 20, 1);
	color: white;
	overflow: auto;
}
main > div {
    padding: 30px;
    width: 90%;
    margin: auto;
    position: relative;
}
.filmsTitle,
.seriesTitle{
    margin-bottom: 50px;
    position: sticky;
    top: 0;
    left: 10%;
    z-index: 1;
    background: rgba(0, 0, 0, 0.8);
    padding: 20px;
    border-radius: 10px;
}
h2{
    font-size: 40px;
}
</style>