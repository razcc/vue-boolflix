<template>
	<div id="filmComp">
		<div>
			<FilmCard :propsToFilmCard="propsToFilmComp" />
		</div>
		<div :class="propsToFilmComp == '' ? 'disBlock' : 'disNone'">
			<h2>Nessun Film disponibile</h2>
		</div>
	</div>
</template>

<script>
import FilmCard from "./Cards/FilmCard.vue";

export default {
	name: "FilmComp",
	props: {
		propsToFilmComp: Array,
	},
	components: {
		FilmCard,
	},
};
</script>

<style lang="scss" scoped>
.disNone {
	display: none;
}
.disBlock {
	display: block;
}
</style>