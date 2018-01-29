<template>
<!-- Il faut avoir qu'un seul élément à la racine (ex 1 div) -->

        <ul>
            <li v-for="(movie, index) in movies_search" v-bind:key="movie.title" v-bind:title="message" @click="movie_to_display=movie">
                <b>{{movie.title}} ({{movie.year}})</b><br />
                <span v-if="movie_to_display === movie">
                    {{movie.synopsys}}<br />
                    <button @click="edit(movie)">Edit</button> <button @click="remove(index)">Remove</button>
                </span>
                <br /><br />
            </li>
        </ul>

<script>
export default {
    data() {
        return {
            message: "Hellox",
            tab : ['test', 'test']
        }
    }
}
</script>

<style>
#msg {
  color: red;
}
</style>