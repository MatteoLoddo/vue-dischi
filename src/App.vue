<template>
  <div id="app">

    <TheHeader :list-genre="genreList"
                @searchGenre="onSearchGenre">
    </TheHeader>

    <main class="my-bg-main p-5">

      <DiscList @genreUpdate="onGenreUpdate"
                :genreSearch="genreSearch"
      ></DiscList>

    </main>

  </div>
</template>

<script>

import TheHeader from "./components/TheHeader.vue";
import DiscList from "./components/DiscList.vue";


export default {

  name: 'App',
  components: { TheHeader, DiscList },
  data(){
    return{
      genreList:[],
      genreSearch:"",

    };
  },

  methods:{
    onGenreUpdate(listGenre){
      this.genreList = listGenre
      console.log(this.genreList);
    },

    onSearchGenre(genre){
      this.genreSearch = genre;
    },
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
.my-bg-main{
    background-color: #1E2D3B;
    height: 100vh;
}
</style>
