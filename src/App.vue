<template>
  <div id="app">
    <HeaderComp @emitQuery="emitQueryFunction"/>
    <MainComp />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'


export default {
	name: "App",
  data(){
    return{
      valoreRicerca: "",
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
};
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app{
  height: 100vh;
}
</style>
