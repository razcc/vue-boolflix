<template>
	<div id="SeriesComp">
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

</style>