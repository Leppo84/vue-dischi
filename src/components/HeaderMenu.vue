<template>
    <header>
        <img alt="Spotify logo" src="../assets/Logo Spotify.png">
        <div class="filter-album">
            <span>Seleziona il genere</span>
            <select v-model="selected" name="genre-selector" id="genre-selector"
                @click="$emit('inputReceived', selected)">
                <option id="opt_all" selected="selected" value="All">All</option>
                <option id="opt_jazz" value="Jazz">Jazz</option>
                <option id="opt_metal" value="Metal">Metal</option>
                <option id="opt_pop" value="Pop">Pop</option>
                <option id="opt_Rock" value="Rock">Rock</option>
            </select>
        </div>
    </header>
</template>

<script>

export default {
  name: 'HeaderMenu',
  data(){
    return{
        selected: "",
    }
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

