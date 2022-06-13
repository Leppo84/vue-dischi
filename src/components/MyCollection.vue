<template>
  <div>      
    <LoadingSplash v-if="collectionLoading">
    </LoadingSplash>
    <div v-else class="container">
      <AlbumCard v-for="(item, index) in filteredAlbums"
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
    props: {
    myGenre: String,
  },
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
  },
  computed: {
      filteredAlbums() {
        if( this.myGenre === "All"){
          console.log(this.myGenre);
        return this.callAlbums;
        }
        else {
          console.log(this.myGenre);
                    return this.callAlbums.filter(item=> {
                      return item.genre.includes(this.myGenre);
        });

          // for (let i = 0; i< this.callAlbums.lenght; i++)
        //   return this.callAlbums.filter(item=> {
        //     if (this.callAlbums.item.genre == this.myGenre) {
        //     return true;
        //     } 
        //     else {
        //       return false;
        //     }
        // })
        }
      }
    },

// const array = [-3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13];

// function isPrime(num) {
//   for (let i = 2; num > i; i++) {
//     if (num % i == 0) {
//       return false;
//     }
//   }
//   return num > 1;
// }

// console.log(array.filter(isPrime)); // [2, 3, 5, 7, 11, 13]

// const ages = [32, 33, 16, 40];
// const result = ages.filter(checkAdult);

// function checkAdult(age) {
// return age >= 18;
// }

  mounted(){
        setTimeout(()=> {
      this.collectionLoading=false;
    },1000);
  },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

div.container {
    display: flex;
    flex-wrap: wrap;
    // align-content: center;
    padding: 40px 0;
    max-width: 60%;
    max-height: calc(100vh - 60px);
    margin: 0 auto;
}

</style>

    <!-- printAlbums(){
    } -->