<template>
	<main>
		<div>
			<div>
				<h2>Films</h2>
			</div>

			<FilmComp :propsToFilmComp="propsFilm" />
		</div>

		<div>
			<h2>Series</h2>
			<SeriesComp :propsToSeriesComp="propsSeries" />
		</div>
	</main>
</template>

<script>
import FilmComp from "./Main Comp/FilmComp.vue";
import SeriesComp from './Main Comp/SeriesComp.vue';

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
</style>