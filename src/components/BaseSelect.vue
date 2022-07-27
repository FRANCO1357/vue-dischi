<template>
    <select v-on:change="myChange" v-model="genreSelected" name="" id="">
        <option v-for="genre in genreArray" :key="genre" :value="genre">{{genre}}</option>
    </select>
</template>

<script>
export default{
    name: 'BaseSelect',
    props: {
        genreArray: Array,
    },
    data(){
        return{
            genreSelected: '',
        }
    },
    methods:{
        myChange(){
            this.$emit('genre-clicked', this.genreSelected)
        }
    }
    
}
</script>

<style lang="scss" scoped>

</style>