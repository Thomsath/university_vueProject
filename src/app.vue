<template>
 <div id="app">
        <span v-if="display">
            {{ message }}
        </span>
        <p>First letter : {{firstletter}}</p>

        <p><input type="text" v-model="message" /></p>    
        <p><button v-on:click="newmovie1">Add "New movie"</button></p>    

        <hr>

        <p>Movie number : {{movies.length}}</p>
        <p>New movie<br />
            Title : <input type="text" v-model="movie_to_add.title" /><br />
            Year : <input type="text" v-model="movie_to_add.year" /><br />
            Synopsys : <textarea v-model="movie_to_add.synopsys"></textarea><br />
            <button v-on:click="newmovie2">Add</button></p>

        Search : <input type="text" v-model="search" />
        
        <p v-if="movie_to_edit">New movie<br />
            Title : <input type="text" v-model="movie_to_edit.title" /><br />
            Year : <input type="text" v-model="movie_to_edit.year" /><br />
            Synopsys : <textarea v-model="movie_to_edit.synopsys"></textarea><br />
            <movieitem v-on:click="save">Save</movieitem></p>

        <h3>Components</h3>
        <ul>
            <movie-item v-for="movie in movies" v-bind:key="movie.title" v-bind:movie="movie"></movie-item>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
       return {
 				message: 'Hello Vue!',
                display: true,
                movie_to_add: {},
                movie_to_edit: undefined,
                movie_to_display: undefined,
                search: "",
                movies : [
                    {
                        title: "L'étrange noël de M. Jack",
                        year: 1994,
                        synopsys: "Jack Skellington, un épouvantail squelettique surnommé « le Roi des citrouilles » (Pumpkin King en version originale), vit dans la ville d'Halloween. En tant que maître de l'épouvante, Jack occupe ses journées à préparer la prochaine fête d'Halloween."
                    }, 
                    {
                        title: "Interstellar",
                        year: 2014,
                        synopsys: "Alors que la Terre se meurt, une équipe d'astronautes franchit un trou de ver apparu près de Saturne conduisant à une autre galaxie, cela dans le but d'explorer un nouveau système stellaire et l'espoir de trouver une nouvelle planète habitable par l'humanité afin de la sauver."
                    }
                ]
            	}
    }
}
</script>

<style>
#msg {
  color: red;
}
</style>