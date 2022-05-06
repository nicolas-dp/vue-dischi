<template>
  <header>
    <nav class="navbar navbar-dark bg_color_dark_side">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="@/assets/spotify.png" alt="" height="50" width="50" />
        </a>

        <SearchBox v-model="searchText" @search="searchText"/>
        
          
        </div>
      
    </nav>
  </header>
</template>

<script>
/* importo il file state in globale */
/* import state from "@/state.js"; */
export default {
  name: "SearchBox",
    data() {
      return {
        searchText : ''
      }
    },

    methods: {
      search(){
        console.log('Searching....');
      } 
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "@/assets/scss/style.scss";
</style>