<template>
  <div class="container">
    <div v-for="(album, index) in callAlbum" class="album-card" :key="index">
        <img :src="album.poster" :alt="album.title">


    </div>

  </div>
</template>

<script>
import axios from "axios"

export default {
  name: 'MyCollection',
  data(){
    return{
        apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
        callAlbums: [],
    }
  },
  created(){
    this.getAlbums();
  },
  methods: {
    getAlbums(){
        axios
        .get(this.apiUrl)
        .then(apiLog => {
            this.callAlbums = apiLog.data.response;
            // console.log(this.callAlbums);
        })
        .catch((error) => {
            console.log("errore", error);
        })
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

div.container {
    display: flex;
    flex-wrap: wrap;
    min-width: 60%;
    height: calc(100vh - 60px);
    // padding-top: 60px;      
}


</style>
obj data
success: true
response: Array(10)
0:
author: "Bon Jovi"
genre: "Rock"
poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
title: "New Jersey"
year: "1988"