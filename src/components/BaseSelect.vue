<template>
    <select v-on:change="myChange" v-model="genreSelected" name="" id="">
            <option v-for="genre in genres" :key="genre.value" :value="genre.value">{{genre.value}}</option>
        </select>
</template>

<script>
export default{
    name: 'BaseSelect',
    data(){
        return{
            genreSelected: '',
            genres: [
                {value: 'Rock'},
                {value: 'Pop'},
                {value: 'Jazz'},
                {value: 'Metal'},
            ],
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