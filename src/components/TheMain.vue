<template>
    <main>
        <div class="container">
            <div class="card" v-for="song in filteredSongs" :key="song.title">
                <TheSongCard :poster="song.poster" :title="song.title" :author="song.author" :year="song.year"/>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios'
import TheSongCard from './TheSongCard.vue';
export default{
    name: "TheMain",
    props: {
        genreSelected: {
            type: String,
            default: '',
        }
    },
    data() {
        return {
            songs: [],
            genres: [],
        };
    },
    mounted() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
            this.songs = res.data.response;
            this.songs.forEach((song) =>{
                if(!this.genres.includes(song.genre)) this.genres.push(song.genre)
            });
            this.$emit('genre-array', this.genres);
        });
    },
    components: { 
        TheSongCard 
    },

    computed: {
        filteredSongs(){
            return this.songs.filter((song) => {
                return song.genre.includes(this.genreSelected)         
            })
        }
    }
}
</script>

<style lang="scss" scoped>
main{
    height: calc(100vh - 60px);
    background-color: #1D2E3B;
    padding: 50px;

    .container{
        width: 1000px;
        min-height: 500px;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;

        .card{
            width: calc(20% - 40px);
            margin: 20px;
            padding: 10px;
            background-color: #2D3B46;
            color: white;
            text-align: center;
        }
}
}
</style>