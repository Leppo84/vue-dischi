<template>
    <header>
        <img alt="Spotify logo" src="../assets/Logo Spotify.png">
    </header>
</template>

<script>
export default {
  name: 'HeaderMenu',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

header {
    width: 100%;
    height: 60px;
    background-color: #2e3a46;
    display: flex;
    flex-wrap: wrap;

    img {
        width: 60px;
        padding: 8px;
        margin: 0 16px;
    }
}

</style>