<template>
        <div class="album-card">
            <img :src="album.poster" :alt="album.title">
            <h4>
                {{album.title.toUpperCase()}}
            </h4>
            <span>{{album.author}}</span>
            <span>{{album.year}}</span>

        </div>
</template>

<script>
export default {
  name: 'HeaderMenu',
  props: {
    album: Object
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    div.album-card {
        display: flex;
        flex-direction: column;
        width: 16%;
        // height: 200px;
        padding: 12px;
        margin: 2%;
        background-color: #2e3a46;

        img {
            max-width: 100%;
            max-height: 100px;
            object-fit: cover;
            object-position: top center;

        }

        h4 {
            margin: 10px auto;
            color: white;
            font-size: small;
        }
        span {
            color: grey;
            font-size: small;
        }
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