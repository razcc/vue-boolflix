<template>
	<div id="SeriesComp">
        <h1>Serie TV</h1>
		<SeriesCard :propsToSeriesCard="propsToSeriesComp" />
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
#SeriesComp {
	display: flex;
	flex-wrap: wrap;
	width: 90%;
	height: 50%;
	margin: auto;
	padding: 30px;
	overflow: auto;
}
</style>