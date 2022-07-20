<template>
    <div class="d-flex justify-content-center mb-5">
        <label class="text-white me-2" for="genres">Choose the music genres: </label>

        <select class="rounded" name="genre" id="genre" v-model="selectedGenre" @change="$emit('search', selectedGenre)">
            <option value="allGenres" selected>All Genres</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal"> Heavy Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            selectedGenre: '',
        }
    }
}
</script>

<style lang='scss' scoped>


</style>