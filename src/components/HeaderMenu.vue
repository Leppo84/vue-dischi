<template>
    <header>
        <img alt="Spotify logo" src="../assets/Logo Spotify.png">
        <div class="filter-album">
            <span>Seleziona il genere</span>
            <select name="genre-selector" id="genre-selector">
                <option id="opt_all" selected="selected" value="all">All</option>
                <option id="opt_jazz" value="jazz">Jazz</option>
                <option id="opt_metal" value="metal">Metal</option>
                <option id="opt_pop" value="pop">Pop</option>
                <option id="opt_Rock" value="rock">Rock</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
  name: 'HeaderMenu',
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
    justify-content: space-between;
    align-items: center;

    img {
        width: 60px;
        padding: 8px;
        margin: 0 16px;
    }

    div.filter-album {
        padding: 8px;
        margin: 0 16px;

        span {
            display: inline-block;
            color: white;
            margin-right: 16px;
        }
        select {
            width: 150px;
        }

    }
}

</style>

