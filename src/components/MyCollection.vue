<template>
  <div>      
    <LoadingSplash v-if="collectionLoading">
    </LoadingSplash>
    <div v-else class="container">
      <AlbumCard v-for="(item, index) in callAlbums"
      :key="index"
      :album="item">
      </AlbumCard>
    </div>
  </div>
</template>

<script>
import axios from "axios"
import AlbumCard from "./AlbumCard.vue"
import LoadingSplash from "./LoadingSplash.vue";

export default {
  name: 'MyCollection',
  components: {
    AlbumCard,
    LoadingSplash
  },
  data(){
    return{
        collectionLoading : true,
        apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
        callAlbums: [],
    }
  },
  created(){
    this.createAlbums();
  },
  methods: {
    createAlbums(){
      axios
        .get(this.apiUrl)
        .then(apiLog => {
          this.callAlbums = apiLog.data.response;
            // console.log(this.callAlbums);
        })
        .catch((error) => {
            console.log("errore", error);
        })
    },
    printAlbums(){
    }
  },
  mounted(){
        setTimeout(()=> {
      this.collectionLoading=false;
    },1500);
  },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

div.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
    max-width: 60%;
    height: calc(100vh - 60px);
    margin: 0 auto;
}

</style>