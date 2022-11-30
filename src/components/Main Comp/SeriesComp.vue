<template>
	<div id="SeriesComp">
		<SeriesCard
			:propsToSeriesCard="propsToSeriesComp"
			:propsLinguaCard="propsLinguaSerie"
			:propsGenereCard="propsGenereSerie"
		/>
		<div :class="propsToSeriesComp == '' ? 'disBlock' : 'disNone'">
			<h2>Nessun Serie disponibile</h2>
		</div>
	</div>
</template>

<script>
import SeriesCard from "./Cards/SeriesCard.vue";

export default {
	name: "SeriesComp",
	props: {
		propsToSeriesComp: Array,
		propsLinguaSerie: String,
		propsGenereSerie: Number,
	},
	components: {
		SeriesCard,
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