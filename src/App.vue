<template>
  <div id="app">
    <HeaderMenu @inputReceived="selectedValue">
    {{wantedGenre}}
    </HeaderMenu>
    <main>
      <!-- <MyCollection :filtered="filterAlbums"> -->
      <MyCollection :genre="wantedGenre">
      </MyCollection>
    </main>
  </div>
</template>

<script>
import HeaderMenu from './components/HeaderMenu.vue'
import MyCollection from './components/MyCollection.vue'


export default {
  name: 'App',
    data(){
    return{
        collectionLoading : true,
        wantedGenre : "all",
    }
  },
  components: {
    HeaderMenu,
    MyCollection,
  },
  methods: {
    selectedValue(selectedGenre) {
      this.wantedGenre = selectedGenre
      // console.log(selectedGenre);
    }
  }
}

</script>

<style lang="scss">
* {
  margin: 0;
  border: 0;
  box-sizing: border-box;
}

main {
  background-color: #1e2d3b;
  text-align: center;
  width: 100%;
  height: calc(100vh - 60px);
}

#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
}

</style>
