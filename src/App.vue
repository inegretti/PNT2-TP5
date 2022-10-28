<template>
  <div id="app">
    <br>
    <!--<Header/>-->
    <NavBar/>
  </div>
</template>

<script>
//import Header from './components/Header.vue'
import NavBar from './components/NavBar.vue'
export default {
  name: 'App',
  components: {
   // Header,
    NavBar,
  }
}
</script>

<style>
#app {
   background: #232323;
	margin: 0;
	font-family: "Montserrat", "Avenir";
}


</style>
