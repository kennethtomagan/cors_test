<template>
  <div id="app">
    <h1>CORS TEST</h1>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Vue from "vue";
export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  mounted(){
        this.$axios
        .get("https://local-searcher.pmstg.com/global/public_search/suburb?like=a")
        .then(response => {
            console.log(response);
        }).catch(error=>{
            console.log(error.response)
        });
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
