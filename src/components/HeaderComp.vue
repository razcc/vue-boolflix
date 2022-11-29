<template>
	<header>
		<img
			src="https://image.tmdb.org/t/p/original/wwemzKWzjKYJFfCeiB57q3r4Bcm.svg"
			alt=""
		/>

		<!-- Search -->
		<div class="btn-group dropstart search">
			<font-awesome-icon icon="fa-solid fa-magnifying-glass dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false"/>
			
            <input type="text" class="dropdown-menu" placeholder="Cerca il tuo Film-Serie">
			
		</div>
	</header>
</template>

<script>
export default {
	name: "HeaderComp",
	components: {},
	data() {
		return {};
	},
};
</script>

<style lang="scss" scoped>
header {
	height: 10vh;
	background: rgb(80, 80, 80);
	background: linear-gradient(
		0deg,
		rgba(80, 80, 80, 1) 0%,
		rgba(0, 0, 0, 1) 100%
	);
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 20px;
}
img {
	height: 50%;
}
.fa-magnifying-glass {
	color: white;
    font-size: 30px;
    margin-right: 50px;
    margin-left: 50px;
}
.dropdown-menu{
    min-width: 20rem;
    border-color: red;
}
</style>