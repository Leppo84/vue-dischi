<template>
  <div id="app">
    <HeaderMenu>
    </HeaderMenu>
    <main>
      <LoadingSplash>
      </LoadingSplash>
      <MyCollection>
      </MyCollection>
    </main>
  </div>
</template>

<script>
import HeaderMenu from './components/HeaderMenu.vue'
import MyCollection from './components/MyCollection.vue'
import LoadingSplash from './components/LoadingSplash.vue'


export default {
  name: 'App',
  components: {
    HeaderMenu,
    LoadingSplash,
    MyCollection,
  },
  data(){
    return{
      collectionLoading : true,
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
