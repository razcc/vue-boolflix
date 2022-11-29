<template>
	<div id="app">
		<HeaderComp @emitQuery="emitQueryFunction" />
		<MainComp />
	</div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import axios from "axios";


export default {
	name: "App",
  data(){
    return{
      valoreRicerca: "",
      urlParziale: "https://api.themoviedb.org/3/search/movie?api_key=ea284f453f6bf939a56b81b5d0741a04&query=ritorno",
      api: [],
    }
  },
	components: {
    HeaderComp,
    MainComp
  },
  methods: {
    emitQueryFunction(emitQueryValore){
      this.valoreRicerca = emitQueryValore
    },
  },
  mounted() {
		axios
			.get('https://api.themoviedb.org/3/search/movie?api_key=ea284f453f6bf939a56b81b5d0741a04&query=${valoreRicerca}')
			.then((response) => {
        console.log(response)
				this.api = response.data.results;			
			});

	},
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
