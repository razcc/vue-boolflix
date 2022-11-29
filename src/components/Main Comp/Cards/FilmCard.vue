<template>
	<div id="filmCard">
		<div v-for="(elem, index) in propsToFilmCard" :key="index">
            {{elem.title}}
        </div>
	</div>
</template>

<script>
export default {
	name: "FilmCard",
	props: {
		propsToFilmCard: Array,
	},
};
</script>

<style lang="scss" scoped>
#filmCard{
    color: white;
}
</style>