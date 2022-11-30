<template>
	<div id="SeriesComp">
		<SeriesCard :propsToSeriesCard="propsToSeriesComp" />
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