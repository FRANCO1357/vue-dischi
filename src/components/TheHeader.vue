<template>
    <header>
        <img src="../assets/spotify_logo.png" alt="">
        <BaseSelect @genre-clicked="getValue" :genre-array="genreArray"/>
    </header>
</template>

<script>
import BaseSelect from './BaseSelect.vue';
export default {
    name: "TheHeader",
    components: { BaseSelect },
    props:{
        genreArray: Array,
    },
    data(){
        return{
        
        }
    },
    methods:{
        getValue(value){
            console.log(1, value)
            this.$emit('genre-clicked', value)
        }
    }
}
</script>

<style lang="scss" scoped>
    header{
        background-color: #2D3B46;
        height: 60px;
        padding: 10px;
        display: flex;
        justify-content: space-between;
        align-items: center;

        img{
            height: 40px;
        }
    }
</style>