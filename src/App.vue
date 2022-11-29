<template>
	<div id="app">
		<HeaderComp @emitQuery="emitQueryFunction" />
		<MainComp :propsFilm="arrayFilm"  :propsSeries="arraySerie"/>
	</div>
</template>

<script>
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";
import axios from "axios";

export default {
	name: "App",
	data() {
		return {
			apiKey: "ea284f453f6bf939a56b81b5d0741a04",
			query: "&query=",
			arrayFilm: "",
			arraySerie: "",
		};
	},
	components: {
		HeaderComp,
		MainComp,
	},
	methods: {
		emitQueryFunction(emitQueryValore) {
			console.log(emitQueryValore);

			// Axios per i film
			axios
				.get(
					"https://api.themoviedb.org/3/search/movie?api_key=" +
						this.apiKey +
						this.query +
						emitQueryValore
				)
				.then((response) => {
					console.log(response);
					this.arrayFilm = response.data.results;
					console.log(this.arrayFilm);
				});

			// Axios per le Serie

			//https://api.themoviedb.org/3/search/tv?api_key=<<api_key>>&language=en-US&page=1&include_adult=false
			axios
				.get(
					"https://api.themoviedb.org/3/search/tv?api_key=" +
						this.apiKey +
						this.query +
						emitQueryValore
				)
				.then((risultato) => {
					this.arraySerie = risultato.data.results;
				});
		},
	},
	mounted() {},
};
</script>

<style lang="scss">
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
#app {
	height: 100vh;
}
</style>
