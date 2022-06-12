<template>
        <div class="album-card">
            <img :src="album.poster" :alt="album.title">
        </div>
</template>

<script>
export default {
  name: 'HeaderMenu',
  props: {
    album: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    div.album-card {
        flex-basis: 20%;
        padding: 10px;
        img {
            max-width: 100%;
        }
    }

</style>